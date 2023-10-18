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

### Averiguar si un puerto esta abierto o no

desde powershell
```
tnc subdominio.pepe.com.pe -port 4370
```
o desde cmd
``` 
tcping subdominio.pepe.com.pe 3389
```


