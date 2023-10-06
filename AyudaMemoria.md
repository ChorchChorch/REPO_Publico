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

## Inventario de cambios
CMD query para obtener fecha cambio de contraseña e inicio de sesion
> net user 	PEPE		/Domain | findstr /r /c:"^ *Nombre de usuario" /c:"^ *Cambio de contraseña"
>
> net user 	PEPE	  /Domain | findstr /r /c:"^ *Nombre de usuario" /c:"^ *Última vez que inició sesión"		
>
> net user 	PEPE	  /Domain | findstr /r /c:"^ *Nombre de usuario" /c:"^ *Directorio principal"

## Obtener un listado de los usuarios locales y su rol
> net user

saber mas detalles sobre el usuario nombreUsuario

>net user nombreUsuario

Activar la cuenta

>net user nombreUsuario /active:yes

Setear la contraseña

>net user nombreUsuario SuperPass

Agregar y borrar ususarios
>Net User nombreUsuario contraseña /add
>
>Net User nombreUsuario /delete

Mas data

•	/COMMENT: permite añadir un comentario en la cuenta de usuario que vamos a crear.

•	/COUNTRYCODE: permite añadir el código del país o región del sistema operativo para usar los archivos de idioma.

•	/EXPIRES: permite configurar cuándo expira una determinada cuenta que vamos a añadir o modificar, si no indicamos nada no expirará nunca.

•	/FULLNAME: esta opción nos permite definir el nombre completo del usuario, y no solamente el nombre de usuario de inicio de sesión.

•	/HOMEDIR: permite configurar la ruta del directorio principal del usuario.

•	/PASSWORDCHG: permite configurar si se permite a los usuarios cambiar su propia contraseña de acceso.

•	/PASSWORDREQ: permite configurar que los usuarios siempre tengan una contraseña de acceso.

•	/LOGONPASSWORDCHG: fuerza al cambio de contraseña del usuario en cuestión en el siguiente inicio de sesión.

•	/PROFILEPATH: establece la ruta para el perfil de inicio de sesión del usuario.

•	/SCRIPTPATH: ubicación del script de inicio de sesión del usuario en cuestión.

•	/TIMES: horas en los que un determinado usuario puede iniciar sesión.

•	/USERCOMMENT: permite agregar o cambiar el comentario de un usuario para la cuenta.

•	/WORKSTATIONS: muestra hasta 8 equipos en la red desde los que podrá iniciar sesión un usuario.

## Monitoreo de Confiabilidad en en un equipo con Windows
Ver en un calendario los problemas, warning etc que se dispararon 

> perfmon /rel

Sino recorrer esta ruta

> Panel de control\Sistema y seguridad\Seguridad y mantenimiento\Monitor de confiabilidad

![confiabilidad Imagen](https://github.com/ChorchChorch/REPO_Publico/blob/master/IM/Monitoreo_Confiabilidad_Issues.JPG)

## Forzar updates Windows
Fuerza las actualizaciones y la descarga inmediata
```
wuauclt.exe /updatenow
```

## Limpieza PC con Windows (adm)
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

### Reiniciar Stack TCP IP (adm)
```
netsh int ip reset
```
Y luego reiniciar PC

### Mapea ruta de red sin persistencia
```
Subst Z: \\192.168.0.1\folder
```

### Upgrade de Lic WIN (adm)
Como saltar el bloqueo que pide cuenta para activar windows, pues dentro del instalador de Windows ejecutandose presionamos Shift + F10 para obtener una consola y tipear **oobe\bypassnro** , reinicias y luego si te permite omitir este paso.
Video de youtube con paso a paso https://youtu.be/xJawqqGomKw
```
REM **obtener Licencia de Windows actual**
wmic path softwareLicensingService get OA3xOriginalProductKey
REM **Cambio de clave**
sc config LicenseManager start= auto & net start LicenseManager
sc config wuauserv start= auto & net start wuauserv
changepk.exe /productkey VK7JG-NPHTM-C97JM-BBBBB-AAAAA
exit
exit
```
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

winget install 7-Zip
winget install adobe.acrobat.reader.64-bit
winget install PDFCreator
winget install Google.Chrome
winget install Microsoft.Teams

winget install videolan.vlc

winget install BleachBit
winget install Microsoft.PowerBI
winget install OBSProject.OBSStudio

winget download Microsoft.PowerBI
```
