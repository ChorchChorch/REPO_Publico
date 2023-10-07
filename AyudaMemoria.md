INDICES

<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#monitoreo-de-confiabilidad-en-en-un-equipo-con-windows">Historial Errores y Warnings</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#limpieza-pc-con-windows-adm">Limpieza PC</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#bateria-notebook">Bateria</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#configurar-los-sitios-de-confianza-navegacion-web">Sitios de Confianza</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#reiniciar-stack-tcp-ip-adm">Reset Stack PC/IP</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#upgrade-de-lic-win-adm">Upgrade Licencia Windows</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#backup-de-drivers-en-windows">Backups dirver Windows</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#inventario-de-cambios">Politica Seguridad</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#excel">Excel</a> | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#listado-de-grandes-clientes-regimen-mipyme">Grandes Clientes (regimen MiPyme)</a>  | 
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#envio-whatsapp-munibot">Envio Whatsapp MuniBOT</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#forzar-updates-windows">Forzar updates Windows</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#aceleracion-hardware-y-recalculo-automatico">Exel aceleracion x hardware</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#habilitar-espacio-virtual">Habilitar espacio virtual</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#password-de-_wifi">Password de WIFI</a> |
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#instalar-programas-por-consola-en-windows">Winget</a> |


### Backup de Drivers en Windows
Backup de driver existentes con PS
```Export-WindowsDriver -Online -Destination c:\driversbkp```

### Fecha de Cambio de Contraseña o Inicio Sesion
> net user  	PEPE   /Domain | findstr /r /c:"^ *Nombre de usuario" /c:"^ *Cambio de contraseña"
>
> net user 	PEPE	  /Domain | findstr /r /c:"^ *Nombre de usuario" /c:"^ *Última vez que inició sesión"
>
> ping	PC01	-n 1

## Envio Whatsapp MuniBOT
> wa.me/3415440147
> 
> https: //api.whatsapp.com/send?phone=3415440147

## EXCEL

### Manejo TXT percepciones

* 33715317619  E  -.----  202309  ADRIAN OSCAR MARQUES DOS SANTOS  DAVID                                                                                                                  -----
* 
* 33715317619  E  -.----  202309  ADRIAN OSCAR MARQUES DOS SANTOS  DAVID JESUS MARQUES DOS SANTOS SOCIEDAD LEY 19550 CAP  I SECC  IV                                                      -----
```
=CONCATENAR(IZQUIERDA(A7,70),REPETIR(" ",110),DERECHA(A7,LARGO(A7)-180))

=CONCATENAR(IZQUIERDA(A6,70),REPETIR(" ",110),DERECHA(A6,LARGO(A6)-180))
```
## Aceleracion Hardware y recalculo automatico

Desde Excel abierto ves a "Archivo" > "Opciones" > "Avanzadas" en el apartado "Mostrar" marca, si no lo está, "Deshabilitar aceleración gráfica de hardware", "Aceptar". 

Cierra Excel y lo vuelves a abrir para comprobar si ha mejorado

### Como agregar a la cinta de opciones el acceso rapido seleccionar solo celdas visibles
![personalizacintaopcionesexel](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/PersonalizarCintaOpcionesEXEL.JPG)

### Listado de Grandes Clientes Regimen MiPYME

https://servicioscf.afip.gob.ar/facturadecreditoelectronica/Listado-RFCE-Mi-PyMe.asp

Imagen ejemplo de AFIP Regimen Grandes CLientes

http://www.afip.gov.ar/afip/resol170204.html
![PagConsultaGrandesClientes](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/GrandesClientes.JPG)

ANEXO I RESOLUCION GENERAL N°1702 DATOS Y CARACTERISTICAS DEL SISTEMA DE IDENTIFICACION DE DATOS DENOMINADO "CODIGO DE BARRAS" A) DATOS Datos que deberá contener el sistema de identificación de datos denominado "Código de Barras":

C.U.I.T. (Clave Unica de Identificación Tributaria) del emisor (11 caracteres).
Código de tipo de comprobante (2 caracteres).
Punto de venta (4 caracteres).
Código de Autorización de Impresión (14 caracteres).
Fecha de vencimiento (8 caracteres).
Dígito verificador (1 carácter). RUTINA PARA EL CALCULO DEL DIGITO VERIFICADOR
Se considera para efectuar el cálculo el siguiente ejemplo: 01234567890

Etapa 1: Comenzar desde la izquierda, sumar todos los caracteres ubicados en las posiciones impares. 0 + 2 + 4 + 6 + 8 + 0 = 20

Etapa 2: Multiplicar la suma obtenida en la etapa 1 por el número 3. 20 x 3 = 60

Etapa 3: Comenzar desde la izquierda, sumar todos los caracteres que están ubicados en las posiciones pares. 1 + 3 + 5+ 7 + 9 = 25

Etapa 4: Sumar los resultados obtenidos en las etapas 2 y 3. 60 + 25 = 85

Etapa 5: Buscar el menor número que sumado al resultado obtenido en la etapa 4 dé un número múltiplo de 10. Este será el valor del dígito verificador del módulo 10. 85 + 5 = 90

De esta manera se llega a que el número 5 es el dígito verificador módulo 10 para el código 01234567890

Siendo el resultado final: 012345678905

### Habilitar espacio virtual
Ejemplo de configiracion de un archivo para deploy rapido, guardar con extension **wsb**
```
<Configuration>
  <VGpu>Enable</VGpu>
  <Networking>Enable</Networking>
  <MappedFolders>
    <MappedFolder>
      <HostFolder>D:\scan</HostFolder>
      <ReadOnly>True</ReadOnly>
    </MappedFolder>
  </MappedFolders>
</Configuration>
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

winget install 7-Zip -silent
winget install adobe.acrobat.reader.64-bit
winget install PDFCreator
winget install Google.Chrome -silent
winget install Microsoft.Teams

winget install videolan.vlc

winget install BleachBit
winget install Microsoft.PowerBI
winget install OBSProject.OBSStudio -silent

winget install Microsoft.Powertoys
winget install Microsoft.WindowsTerminal

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
### Tomar el control de una carpeta
https://norfipc.com/utiles/como-administrar-cambiar-permisos-archivos-carpetas-windows.html

#### W7
```
CALCS "D:\DATOS" /E /G Pepe:F
```
O navegar con el cmd y posicionarte en esa carpeta puntual, entonces podes omitir el destino 
```
CALCS /E /G Pepe:F
```
Para denegarle el acceso a los mismos archivos al usuario Andres:
```
CALCS  /D Andres
```
Para darle solo el permiso de leer el contenido de dichos archivos al usuario José:
```
CALCS  /P Jose:R
```
#### W8 y W10 W11
```
TAKEOWN /F "D:\System Volume Information" /R
```
