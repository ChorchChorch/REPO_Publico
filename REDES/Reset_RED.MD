@echo off

title Reset de conectividad Windows
 
echo ======================================

echo RESET DE RED Y CONECTIVIDAD

echo ======================================

echo.

echo [1/9] Sincronizando hora...

w32tm /resync

echo.

echo [2/9] Mostrando configuracion IP actual...

ipconfig /all

echo.

echo [3/9] Limpiando cache DNS...

ipconfig /flushdns

echo.

echo [4/9] Limpiando cache NetBIOS...

nbtstat -R
 
echo.

echo [5/9] Reiniciando Winsock...

netsh winsock reset
 
echo.

echo [6/9] Reiniciando pila TCP/IP...

netsh int ip reset
 
echo.

echo [7/9] Restableciendo configuracion WinHTTP Proxy...

netsh winhttp reset proxy
 
echo.

echo [8/9] Renovando direccion IP...

ipconfig /release

ipconfig /renew
 
echo.

echo [9/9] Probando conectividad...

ping 8.8.8.8 -n 4

ping google.com -n 4

echo.

echo ======================================

echo Operacion finalizada.

echo La PC se reiniciara en 15 segundos.

echo ======================================

shutdown /r /t 15




echo ============================= PLUSS =============================
netsh winhttp show proxy

netsh winhttp reset proxy


netsh interface show interface

route print

ipconfig /all

