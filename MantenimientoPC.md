# Hilo para mantenimiento de PC
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#monitoreo-de-confiabilidad-en-en-un-equipo-con-windows">HistoricoConfiabilidad</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#forzar-updates-windows">UpdateWindows</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#backup-de-drivers-en-windows">BackupDrivers</a> |<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#impresora"> Impresora</a>


<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#zocalos-de-memoria-de-una-motherboard">RAM</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#mapea-ruta-de-red-sin-persistencia">UnidadDisco</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#bateria-notebook">Bateria</a> | 

<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#limpieza-pc-con-windows">LimpiezaPC</a> 


<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#configurar-los-sitios-de-confianza-navegacion-web">ConfiazaNavegacion</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#reiniciar-stack-tcp-ip">TCP_IP</a> | 

 | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#password-de-_wifi">PasswordWifi</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#instalar-programas-por-consola-en-windows">Winget</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#instalaci%C3%B3n-de-winget-en-espacio-aislado-de-windows">EspacioAislado</a>





## Monitoreo de Confiabilidad en en un equipo con Windows
Ver en un calendario los problemas, warning etc que se dispararon 
```
perfmon /rel
```
Sino recorrer esta ruta

> Panel de control\Sistema y seguridad\Seguridad y mantenimiento\Monitor de confiabilidad

![confiabilidad Imagen](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/Monitoreo_Confiabilidad_Issues.JPG)

## Forzar updates Windows
Fuerza las actualizaciones y la descarga inmediata
```
wuauclt.exe /updatenow
```

## Limpieza PC con Windows
Veamos las *tareas en segundo plano*  y tambien *administrador de tareas* solapa inicio, luego:
```
start cleanmgr.exe
start %temp%
start C:\Windows\Temp
cls

systeminfo
 
DISM /Online /Cleanup-Image /checkhealth
DISM /Online /Cleanup-Image /ScanHealth
DISM /Online /Cleanup-Image /restorehealth
 
sfc /scannow
gpupdate /force
gpresult -r
```
### Zocalos de memoria de una MotherBoard
```
wmic memphysical get MaxCapacity, MemoryDevices
wmic memorychip get devicelocator, capacity
```
![RAM_ZOCALOS](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/RAM_ZOCALOS.JPG)

### Bateria Notebook
```
powercfg /batteryreport
```

### Configurar los sitios de confianza navegacion web
```
start inetcpl.cpl
```

### Reiniciar Stack TCP IP
```
netsh int ip reset
```
Y luego reiniciar PC

### Mapea ruta de red sin persistencia
```
Subst Z: \\192.168.0.1\folder
```
### Backup de Drivers en Windows
Backup de driver existentes con PS
```
Export-WindowsDriver -Online -Destination c:\driversbkp
```
### Password de _WiFi
Listar todas las redes Recordadas
Preguntar por la aue nos interesa
```
netsh wlan show profile
netsh wlan show profile name=nombredelperfil key=clear
```
### Instalar programas por consola en Windows
Winget Instalar programas por consola en Windows. Solo puede correr una instancia de winget 
Referencias en https://github.com/microsoft/winget-cli/releases/
BleachBit, alternativa a CCLeaner lic free GPL
```
winget update
winget upgrade

winget search acrobat

winget install 7-Zip --silent
winget install adobe.acrobat.reader.64-bit
winget install PDFCreator
winget install Google.Chrome --silent
winget install Microsoft.Teams

winget install videolan.vlc

winget install BleachBit
winget install Microsoft.PowerBI
winget install OBSProject.OBSStudio --silent

winget install Microsoft.Powertoys
winget install Microsoft.WindowsTerminal --silent

winget download Microsoft.PowerBI
```
### Instalación de winget en Espacio aislado de Windows
https://learn.microsoft.com/es-es/windows/package-manager/winget/#install-winget-on-windows-sandbox
Espacio aislado de Windows proporciona un entorno de escritorio ligero para ejecutar aplicaciones de forma segura y de forma aislada. El software instalado dentro del entorno de Espacio aislado de Windows permanece "aislado" y se ejecuta por separado desde el equipo host. El Espacio aislado de Windows no dispone de winget ni de la aplicación de Microsoft Store, por lo que tendrá que descargar el paquete winget más reciente de la página de versiones de winget en GitHub.

Para instalar la versión estable de winget en Espacio aislado de Windows, siga estos pasos desde un símbolo del sistema de Windows PowerShell:
```
$progressPreference = 'silentlyContinue'
Write-Information "Downloading WinGet and its dependencies..."
Invoke-WebRequest -Uri https://aka.ms/getwinget -OutFile Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle
Invoke-WebRequest -Uri https://aka.ms/Microsoft.VCLibs.x64.14.00.Desktop.appx -OutFile Microsoft.VCLibs.x64.14.00.Desktop.appx
Invoke-WebRequest -Uri https://github.com/microsoft/microsoft-ui-xaml/releases/download/v2.7.3/Microsoft.UI.Xaml.2.7.x64.appx -OutFile Microsoft.UI.Xaml.2.7.x64.appx
Add-AppxPackage Microsoft.VCLibs.x64.14.00.Desktop.appx
Add-AppxPackage Microsoft.UI.Xaml.2.7.x64.appx
Add-AppxPackage Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle
```

### Impresora
```
net stop spooler
cd C:\WINDOWS\system32\spool\PRINTERS
del *
net start spooler
```

###  Modo Dios y similares
todas las funciones
```
explorer.exe shell:::{ED7BA470-8E54-465E-825C-99712043E01C}
```
modo dios
```
explorer.exe shell:::{ED7BA470-8E54-465E-825C-99712043E01C}
```
Certificados del sistema
hidden C:\Users\%username%\AppData\Roaming\Microsoft\SystemCertificates
```
shell:SystemCertificates
```
Listado de APP de windows importantes
```
C:\Windows\explorer.exe shell:common administrative tools
```
### ver istado de programas Instalados

```
wmic /node:IP /user:usuario product get name,version,vendor
```
y para sacar la salida a un archivo
```
/output:D:\aplicaciones_instaladas.txt product get name,version
```
o en HTML o sumar la ruta de instalacion (installlocation)
```
/output:D:\aplicaciones_instaladas.html product get name,version,installocation
```
