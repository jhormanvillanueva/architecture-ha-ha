# Implementar una arquitectura segura, de alta disponibilidad y escalable en AWS.

En esta guía, configuraré una Virtual Private Cloud (VPC) para implementar un servidor web basado en Python y una base de datos MySQL en una arquitectura segura, de alta disponibilidad y escalable.

![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![AWS](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)

## Se va a implementar la arquitectura de nube en AWS de la siguiente imagen. 
![arquitectura aws](img/arq-hs-ha.gif)

<hr>
1. Se configura la infraestructura de red utilizando el servicio AWS VPC.

- Voy a crear una VPC con el siguiente bloque CIDR IPv4
- 192.168.0.0/16

- Voy a crear las seis subredes con los siguientes nombres:
- **PublicSubnetA**:
- Zona de disponibilidad: a
- CIDR: 192.168.1.0/24

- **PublicSubnetB**:
- Zona de disponibilidad: b
- CIDR: 192.168.2.0/24

- **PrivateSubnetA**:
- Zona de disponibilidad: a
- CIDR: 192.168.3.0/24

- **PrivateSubnetB**:
- Zona de disponibilidad: b
- CIDR: 192.168.4.0/24

- **PrivateSubnetAA**:
- Zona de disponibilidad: a
- CIDR: 192.168.5.0/24

- **PrivateSubnetBB**:
- Zona de disponibilidad: b
- CIDR: 192.168.6.0/24

Como se necesita que la VPC tenga una conexión a Internet, se debe configurar un **Internet Gateway**.
- Cuando se crea el Internet Gateway, se conecta a la VPC
- Creo una tabla de enrutamiento (Route Table)
- En la Route Table asocio las dos **subredes públicas** y creo una ruta para permitir la conexión a Internet a través del **Internet Gateway**

<hr>
