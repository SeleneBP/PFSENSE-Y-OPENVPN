# INSTALACIÓN PROXMOX

- Creamos una máquina virtual en Oracle VM VirtualBox.
El sistemas operativo le indicaremos que será un Debian 11 Bullseye, pero es indiferente.
La imagen ISO que utilizaremos será la de Proxmox 7.4 Aquí esta el enlace de descarga de todas las imaganes, en mi caso se utilizaría la última versión estable: [Descargar imagen ISO](https://www.proxmox.com/en/downloads)
En memoria Ram le pondremos en mi caso 4GB para que vaya un poco más rápido.
Y por último tenemos que cambiarle la red, por defecto en esta en NAT, lo pondremos en adaptador puente, para que tenga salida a internet. 

**Muy importante!!**, tenemos que seleccionar por donde tendrá salida a internet si por Wifi o por cable, en mi caso es por Wifi, pero hay que tenerlo muy en cuenta porque si no puede dar problemas de red.

![image](imagenes/1-instproxmox.png)

- Iniciamos la máquina.
Le damos a instalar.

![image](https://user-images.githubusercontent.com/91204696/236176864-ab628bbc-5cf1-4703-83ce-dc2431ad46b5.png)

Acaptamos los términos.

![image](https://user-images.githubusercontent.com/91204696/236177326-7bb8a5d9-7a9c-42d6-89d2-78249040a118.png)

Ponemos la unidad del disco que queremos.

![image](https://user-images.githubusercontent.com/91204696/236177344-14822281-42e4-42b0-9635-b40d4d246d0a.png)

Seleccionamos el país, la zona horaria y el teclado.

![image](https://user-images.githubusercontent.com/91204696/236184255-71487033-89e2-4e23-88b4-1256b16bb917.png)

Ponemos una contraseña y el correo electrónico.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/bb170914-4a95-4a50-8e33-f45d5d04ff87)

Ponemos la interfaces, la ip, gateway y el dns del servidor.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/614cd3bc-8462-40f1-a432-192198c1e002)

En la siguiente imagen, vemos el resumen de todos lo que hemos configurado y le daremos a instalar.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/9c7e2b7c-3f7b-4fae-b840-2e1291b2404d)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/60e39e4f-7bda-49ca-8996-f35bf0315457)

Una vez que se haya instalado volverá a la pantalla de instalación de proxmox, en ese momento apagamos la máquina y le quitamos la ISO.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/d1bdd9f2-0f3e-4a1d-aecf-6c509c4bbb42)

Una vez que tengamos instalado el proxmox y quitado la iso, ya podremos meternos desde el navegador a proxmox con su ip.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/6ec638f8-74ec-4665-ac23-18b414ee5c76)

Tendremos que hacer un paso previo si queremos actualizar los paquetes.
Tenemos que irnos dentro de pve a Repositorios y quitar los repositorios que son de Enterprise, es decir, que se necesita licencia, sino lo quitamos no podrá actualizar nada, dará error todo el tiempo.
Le damos agregar y seleccionamos la opción de no-subscription.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/08e4082d-d551-4c23-a7b8-73437140fe39)

Ahora arriba de Repositorios en Actualizaciones le damos a refrescar hasta que salga task ok.

En proxmox modo comando actualizaremos también con update y updagrade.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/f923e887-3d9a-40f0-af73-bfac24b7531e)

Ahora para que en proxmox se nos actualicen las plantillas y nos salgan unas cuantas más pondremos el siguiente comando.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/b433e72d-4056-4064-a5cb-749731cb88aa)

Ahora veremos que hay una sección de plantillas de turnkey.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/7d0dc4a5-e328-4787-babf-dc1c2da28f85)

-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.

