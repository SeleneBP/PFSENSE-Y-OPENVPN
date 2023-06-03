# INTEGRAR PROXMOX EN PFSENSE

Lo que tenemos que hacer es apagar el proxmox y añadir una tarjeta de red que está sea la de pfsense, en red interna.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/169aac47-b7c0-432e-bf6c-84a382788662)

Encendemos proxmox y hacemos ip a.

Veremos que tenemos que encender la tarjeta de red.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/8de32867-5ffd-4dab-9918-fe69d478f6bf)

Pero eso no será suficiento, porque pfsense no tiene que dar una IP. Nos metemos en `/etc/network/interfaces`, ponemos la `enp0s8` como dhcp. Reiniciamos y hacemos ip a.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/b6e97c6e-aa5a-41f5-a184-1b7f752c6636)

Vemos que nos ha dado una ip del rango de ip que pusimos en la configuración de pfsense.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/45ac08c0-4009-4fa4-ac2d-b43242ad3398)

Ahora podemos entrar al proxmox desde una máquina virtual con la red de pfsense, es decir, hay más seguridad.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/b317b28b-8926-48b8-b857-88a9e5a11ed4)

PERO, también podremos entrar desde nuestra red a proxmox. (La ip para entrar a proxmox cambia dependiendo de donde quieras entrar, si desde pfsense, red 192.168.100.101:8006 o desde la máquina normal proxmox red 192.168.1.120:8006)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/8e780b3d-7718-4f3f-8dd6-6c99e454a19e)
