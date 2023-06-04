# INTRODUCCIÓN TEÓRICA

La virtualización de servidores se ha convertido en una solución utilizada por muchos entornor empresariales, por la gran capacidad para consolidar recursos, 
aumentar la eficiencia y reducir costos. Para ello he utilizado Proxmox, como plataforma de virtualización por ser de código abierto. 

A continuación, se profundizará en el concepto VPN y se presentarán los principios y protocolos utilizados para establecer conexiones seguras 
a través de redes públicas, como Internet. Se identificarán los aspectos clave a considerar al implementar una solución de VPN y control de acceso a los usuarios.
- Protocolo UDP (1194): Es utilizado en OpenVPN y en el firewall pfSense para establecer conexiones VPN (Redes Privadas Virtuales) de manera segura y eficiente. A diferencia del protocolo TCP, que es más orientado a la conexión y garantiza la entrega ordenada y confiable de los paquetes de datos.
- VPN: Permite establecer una conexión segura y privada a través de una red pública, como Internet. Básicamente, una VPN crea un túnel cifrado entre un dispositivo (como una computadora, teléfono o tablet) y un servidor remoto, lo que te permite enviar y recibir datos de manera segura.
- Pfsense: Es un sistema operativo de código abierto basado en FreeBSD que se utiliza comúnmente como un firewall y enrutador de red. 
