# Hilo para mantgenimiento de PC

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
### Backup de Drivers en Windows
Backup de driver existentes con PS
```Export-WindowsDriver -Online -Destination c:\driversbkp```




