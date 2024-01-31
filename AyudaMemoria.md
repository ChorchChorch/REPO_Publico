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
<a href="https://github.com/ChorchChorch/REPO_Publico/blob/master/AyudaMemoria.md#instalar-programas-por-consola-en-windows">Winget</a> 

## Envio Whatsapp MuniBOT
> wa.me/3415440147
> 
> https: //api.whatsapp.com/send?phone=3415440147

## Abreviaturas de oficina
PTO (paid time off) - Día libre pagado
ASAP (as soon as posible) - Tan pronto como sea posible
AFK (away from keyboard) - Me alejo de la computadora
BRB (be right back) - Ya vuelvo
All hands - Toda la empresa
Milestone - Hito

## EXCEL

### Manejo TXT percepciones

* 33715317619  E  -.----  202309  ADRIAN OSCAR MARQUES DOS SANTOS  DAVID                                                                                                                  -----
* 
* 33715317619  E  -.----  202309  ADRIAN OSCAR MARQUES DOS SANTOS  DAVID JESUS MARQUES DOS SANTOS SOCIEDAD LEY 19550 CAP  I SECC  IV                                                      -----
```
=CONCATENAR(IZQUIERDA(A7,70),REPETIR(" ",110),DERECHA(A7,LARGO(A7)-180))

=CONCATENAR(IZQUIERDA(A6,70),REPETIR(" ",110),DERECHA(A6,LARGO(A6)-180))
```
### Agregado de Punto en Productos
```
SI(LARGO(H1)>12;H1;SI(LARGO(H1)<=9;CONCATENAR(IZQUIERDA(H1;4);".";DERECHA(H1;5));SI(LARGO(H1=12);CONCATENAR(IZQUIERDA(H1;6);".";DERECHA(H1;6)))))
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

### cambio entre multiples paantallas de escritorios W 10
El manejo de ventanas que nos solicitas en Windows 10 , puedes hacerlo de la siguiente forma para trasladar ventanas de un escritorio a otro utilizando el ratón de tu equipo.
![](https://imgmedia.larepublica.pe/640x371/larepublica/original/2021/12/13/61b7485eb6169e3ab739454b.webp)
Realiza esto:

Crea uno o más escritorios en tu equipo presionando la teclas Windows +Control+D.

Abre la ventana que quieres trasladar.
Visualiza los escritorios en la parte inferior de la pantalla con las teclas Windows +Tab (Tabulador).
Traslada la ventana de un escritorio a otro arrastrandola con el punetro del ratón. 
De esta forma puedes trasladar una ventana de un escritorio a otro. Si quieres moverte entre escritorios presiona las teclas Control + Windows +Tecla de dirección, izquierda o derecha.

### rewinicio conytolador de video teclas

Ctrol + Shift + WIN + B

[alñternayiva a reibiviar](https://www.wikihow.com/images/thumb/0/02/Reset-Graphics-Driver-Step-1-Version-2.jpg/v4-728px-Reset-Graphics-Driver-Step-1-Version-2.jpg.webp)

### celu viejo como antena wifi


### Busqueda en GOOGLE

" " Con todas las palabras
- Sin las palabras
AND Conector Booleano busca Palabra1 y Palabra2
OR Palabra2 Conector Booleano busca Palabra1 o Palabra2
filetype: Búsqueda por tipo de archivo
site: Búsqueda por Dominio
intitle: Búsqueda en el título
allinurl: Búsqueda solo en la URL
allintext: Búsqueda solo en el texto
allintitle: Búsqueda solo en el título
allinanchor: Búsqueda en los links de la página
~ Sinónimos
* Cercanía
+ Inclusión
define: Significados

