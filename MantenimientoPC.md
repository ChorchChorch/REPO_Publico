# Hilo para mantenimiento de PC
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#monitoreo-de-confiabilidad-en-en-un-equipo-con-windows">HistoricoConfiabilidad</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#forzar-updates-windows">UpdateWindows</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#backup-de-drivers-en-windows">BackupDrivers</a> |<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#impresora"> Impresora</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#estado-smart-de-discos-rigidos"> S.M.A.R.T. HDD</a>

<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#zocalos-de-memoria-de-una-motherboard">RAM</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#mapea-ruta-de-red">UnidadDisco</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#bateria-notebook">Bateria</a> | 

<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#limpieza-pc-con-windows">LimpiezaPC</a> 

<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#configurar-los-sitios-de-confianza-navegacion-web">ConfiazaNavegacion</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#reiniciar-stack-tcp-ip">TCP_IP</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#test-de-conexion-a-bd"> Conexta a DB </a>

 | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#password-de-_wifi">PasswordWifi</a> | <a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#instalar-programas-por-consola-en-windows">Winget</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/MantenimientoPC.md#instalaci%C3%B3n-de-winget-en-espacio-aislado-de-windows">EspacioAislado</a>

### Video reparar Store de MS
https://youtu.be/PunBh9WFk4s

### BCUninstaller 
Es un desinstalador de programas para Windows de código abierto que cuenta con funciones avanzadas de limpieza. Cuando desinstalamos un programa desde Windows, este suele dejar en el sistema todo tipo de archivos residuales repartidos por el disco duro.

Gracias a BCU, vamos a poder eliminar todo tipo de aplicaciones y juegos, forzando al sistema a eliminar todos los datos residuales que ha dejado el programa en nuestro ordenador. Además, es el propio programa el que detecta y elimina todos estos datos, por lo que nosotros no tendremos que hacer nada para llevar a cabo la limpieza.

https://www.bcuninstaller.com/

## Monitoreo de Confiabilidad en en un equipo con Windows
Ver en un calendario los problemas, warning etc que se dispararon 
```
perfmon /rel
```
Sino recorrer esta ruta

> Panel de control\Sistema y seguridad\Seguridad y mantenimiento\Monitor de confiabilidad

![confiabilidad Imagen](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/Monitoreo_Confiabilidad_Issues.JPG)

## Estado Smart de Discos Rigidos
```
WMIC /Output:STDOUT diskdrive get status
```

## Limpieza PC con Windows
En el buscador de windows escribis "Sensor de almacenamiento". Te a permitir borrar informacion vieja guardada
Veamos las *tareas en segundo plano*  y tambien *administrador de tareas* solapa inicio, luego:
```
# Fecha de ultimo reinicio
(gcim Win32_OperatingSystem).LastBootUpTime
# Fecha de instalacion  de Windows
(Get-CimInstance -Class Win32_OperatingSystem).InstallDate
# Estado de HDD
Get-PhysicalDisk | Format-Table -AutoSize
```
CMD
```
start cleanmgr.exe
start %temp%
start C:\Windows\Temp
cls

REM Zocalos de memoria de una MotherBoard
wmic memphysical get MaxCapacity, MemoryDevices
wmic memorychip get devicelocator, capacity , memorytype
REM Valores posibles para memorirytipe -> 21 es DDR2 , 24 es DDR3 , 26 es DDR4 y 30 es DDR5

REM Testea memoria RAM
start mdsched.exe

systeminfo
 
DISM /Online /Cleanup-Image /checkhealth
DISM /Online /Cleanup-Image /ScanHealth
DISM /Online /Cleanup-Image /restorehealth
 
sfc /scannow
sigverif
gpupdate /force
gpresult -r
```
### Ejecucion de un benckmark
La consola de Windows ejecuta un benchmark completo que analiza el rendimiento del equipo y todos sus componentes. Este comando, el WINSAT, también puede ser acompañado de otros apellidos más allá de FORMAL, como por ejemplo CPUFORMAL para medir sólo el rendimiento de la CPU, MEMFORMAL para el de la RAM, GRAPHICSFORMAL para la tarjeta gráfica o DISKFORMAL para las unidades de almacenamiento.
```
WINSAT FORMAL
```
![RAM_ZOCALOS](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/RAM_ZOCALOS.JPG)
![SMART HDD con PowerShell](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/SMART_HDD.JPG)

### detectar errores en la memoria RAM del PC
Abrira una ventana de Windows preguntando si queres correrlo de manera inmedia (reiniciando) o en el porximo reinicio 
```
mdsched.exe
```

### Bateria Notebook
```
powercfg /batteryreport
REM Para deshabilitar la hibernación
POWERCFG -H OFF
```

### Configurar los sitios de confianza navegacion web
```
start inetcpl.cpl
```
### CMD administrar usuarios
```
para listar ususarios
Net User 
Pisar la contraseña de usuario existente. Nombre de ususario logitud max 20 caracteres
Net User <nombreUsuario> <Contraseña> 
O con asterisco toma de manera interactiva (por cmd) unanueva contraseña
Net User <nombreUsuario> *
agregar nuevo uusario
Net User <nombreUsuario> <Contraseña> /add 
activar ususario
Net User <nombreUsuario> /active
Para lanzar la capa grafica de usuarios
control userpasswords2
```

### Hardening Celulares Android - MDM
MDM, es la abreviatura de Mobile Device Management y para eso a bajo costo tenes **AppLock** con capa gratis (con publicidad) sino valia alrededor de 3 dolares
Ver como es el tema de licienciamiento
https://play.google.com/store/apps/details?id=com.domobile.applockwatcher&hl=es_AR&pli=1

### Reiniciar Stack TCP IP
```
netsh int ip reset
```
Y luego reiniciar PC

### Mapea ruta de red 
Sin persistencia
```
Subst Z: \\192.168.0.1\folder
```
Con persitencia
```
NET USE Z: \\server\datos /PERSISTENT:YES
NET USE f: \\server\datos /PERSISTENT:YES /user:dominio\user password
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
### Desinstalar por consola
```
winget uninstall Zoom.Zoom --silent
```

### Todos los comandos CPL y otros en CMD
https://protegermipc.net/2016/08/30/archivos-cpl/

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

### Windows defender por CMD

https://www.softzone.es/programas/antivirus/buscar-virus-cmd-windows-defender/


Actualizar firma de virus
```
C:\Program Files\Windows Defender>MpCmdRun.exe -SignatureUpdate
```
Tipos de scan0: análisis por defecto.
1: análisis rápido.
2: análisis completo del PC.
3: análisis personalizado con un directorio propio.


Scan Full
```
C:\Program Files\Windows Defender>MpCmdRun.exe -scan -2
```
Scan Rapido
```
C:\Program Files\Windows Defender>MpCmdRun.exe -scan -1
```
```
C:\Program Files\Windows Defender>MpCmdRun.exe -Scan -3 -File "C:\Usersusuario"
```

```
MpCmdRun -Scan -ScanType -BootSectorScan
```

Posteriormente, vamos a ejecutar el siguiente comando para poder desinstalar las definiciones más recientes:

```
MpCmdRun -RemoveDefinitions -All
```
La opción -All se encargará de restaurar las actualizaciones anteriores del antivirus de Microsoft.

Igualmente, podemos desinstalar solo las firmas dinámicas, escribiendo el siguiente comando y pulsando Enter:

```
MpCmdRun -RemoveDefinitions -DynamicSignatures
```
Cancelar tareas en marcha

En el caso de que hayamos ejecutado por error un comando y Windows Defender ha empezado a analizar nuestro PC posiblemente nos echaremos las manos al a cabeza. Y es que, al no tener la interfaz abierta, no podremos controlar la actividad del antivirus desde ella. Sin embargo, podemos echar mano de un truco gracias al cual vamos a poder detener cualquier escaneo manual que se encuentre en marcha. Para ello, simplemente debemos ejecutar este comando para detener todo lo que haya en ejecución:

```
MpCmdRun -Cancel
```

--------
También desde PowerShell
PowerShell es la evolución de la línea de comandos de Windows creada para cubrir las carencias que ofrecía CMD a la hora de trabajar en redes. Gracias PowerShell, los administradores de sistemas pueden acceder de forma remota a equipos a través de scripts y ejecutar múltiples comandos y múltiples dispositivos a la vez. Teniendo en cuenta esta funcionalidad, obviamente con PowerShell también podemos buscar virus en el equipo, al igual que actualizar el antivirus.

Lo primero que debemos hacer para acceder a PowerShell y analizar el equipo en busca de virus es ejecutar la aplicación como administrador y actualizar Windows Defender para asegurarnos que está preparado para detectar las vulnerabilidades más recientes. Para ello, utilizamos el comando

```
Update-MpSignature
```
Para analizar el equipo en busca de virus, el comando que vamos a utilizar es el siguiente para realizar un escaneo rápido:

```
Start-MpScan -ScanType QuickScan
```
Buscar Viurus PowerShell

Pero, si queremos realizar un escaneo en profundidad para verificar todos y cada uno de los archivos que forman parte de nuestro equipo, debemos sustituir en el comando anterior, QuickScan por FullScan. Este proceso lleva mucho más tiempo, por lo podemos dejar el ordenador trabajando en segundo plano sin cerrar la ventana de PowerShell.

```
Start-MpScan -ScanType FullScan
```
A través de PowerShell podemos crear un script que se ejecute periódicamente para que, a partir de determinada hora, analice el equipo en busca de software malicioso.

El comando que debemos utilizar para hacer un escaneo rápido sería:

```
Set-MpPreference -ScanScheduleQuickScanTime 22:00:00
```
Para realizar un escaneo completo, el comando sería el siguiente:
```
Set-MpPreference -ScanScheduleFullScanTime 22:00:00
```

### Contraseñas guardadas en Windows
No se cual seria la diferencia con el baul de contraseñas pero aqui va.(revise y es lo mismo)
Abriremos una nueva ventana de Ejecutar y escribiremos la sentencia que mostramos a continuación.
```
rundll32.exe keymgr.dll, KRShowKeyMgr
```
Aparecerá una nueva ventana emergente llamada Nombres de usuario y contraseñas almacenadas.
![ListaContrasenas](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/ClavesGuardadasWindows.JPG)

### Test de conexion a BD
Crear un archivo y renombrarlo con la extension UDL

![TestConexionBD](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/TestConexionBD_UDL.jpg)

### Administrador de Hardware
```
devmgmt.msc  
```
### Relevamiento de Flota
```
Get-WmiObject Win32_OperatingSystem -ComputerName 127.0.0.1
Get-WmiObject Win32_ComputerSystem -ComputerName 127.0.0.1
Get-WmiObject Win32_BIOS -ComputerName 127.0.0.1
Get-WmiObject Win32_LogicalDisk -Filter "DeviceID='C:'" -ComputerName 127.0.0.1
getmac /s 127.0.0.1
```


### Desconectarse de la PC sin reiniciarla
Cierra la sesión del usuario con el que estás accediendo al ordenador, aunque manteniendo el ordenador encendido.
```
LOGOFF
```
