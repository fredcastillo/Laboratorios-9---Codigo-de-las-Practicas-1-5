## Preparacion de la VM



ssh root@164.90.146.162

yum update -y
yum install wget -y



## Instalacion de Issabel



wget http://repo.issabel.org/issabel5-netinstall.sh
chmod +x issabel5-netinstall.sh

ejecutar con: ./issabel5-netinstall.sh
Elegir: Asterik 18
Elegir: las dos primeras ops
Clave de MariaDB: 1234
Clave del usuario admin: fred123



## Apagar Fail2Ban



systemctl stop fail2ban
systemctl disable fail2ban

## 

## Configuracion Web



En el navegador: https://164.90.146.162
Login: usuario admin y la password
Crear las extensiones: PBX -> PBX Configuration
Aplicaciones -> Extensiones
En el tipo de dispositivo seleccionar SIP (5066)

Extension 1 (yo):
2221
Display name: fred
Abrir y poner 5066 en el puerto
En nat ponerlo que si
Bajar al final y darle a Submit

Extension 2 (Profe):
2220
Display name: Profe
Secret: Teletubies123$
Abrir y poner 5066 en el puerto
En nat ponerlo que si
Bajar al final y darle a Submit

Darle a Apply Configuration

## 

## Zoiper en el celular



Descargar Zoiper en el celular
Ajustes
Cuenta, +
Si
manualmente
Cuenta SIP
nombre de cuenta cualquiera
dominio IP\_VM:5066
usuario la\_extension
password si tiene
identificador la\_extension

