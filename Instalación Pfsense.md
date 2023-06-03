# INSTALACIÓN PFSENSE

Configuramos la máquina como se muestra en la siguiente imagen.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/0ee52d35-512b-4950-8ece-51b63293d2b7)

**IMPORTANTE!!**
Tendremos que tener dos adaptadores. El primero será la WAN y es la que sale a internet y el segundo adaptador de red será la LAN y será la red interna, donde podremos conectar con otras máquinas.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/99655909-f200-4f15-bd01-898ee172415b)


![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/5d0c5889-1ad5-4cb0-b13a-1ed9366d920d)

Le damos a iniciar la máquina y comenzará la instalación. Dejamos todos los valores por defecto en la instalación.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/9e112cb2-4fa0-4b93-95a4-384b9574396a)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/0588044c-8f62-4ef9-9f50-1cdde09eded5)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/6a577676-2e2e-4ff6-a9bf-9a42ea1e725c)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/75dc8c9d-2f02-46d8-9bbc-eac8c7f9074b)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/e04aa8ac-b04f-4c2a-93ac-fc2e1dc0b807)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/9b0549de-a1a7-4f70-8e1d-0ce19cccc8ac)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/9e79845f-2d5b-46f5-a398-67a7480ed0bb)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/2ab47a54-5287-4ebd-8648-abecb1b1bdf2)

Ya solo falta esperar a que se instale y le damos a reiniciar

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/ff2ae451-670b-4318-b2f2-f9294eb236e3)

Nos saldrá una pantalla donde nos preguntará si queremos hacer alguna configuración más, le damos que no.

Y en la siguiente pantalla nos aparecerá un mensaje para reiniciar, le damos.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/61358fa7-c087-4c41-8565-182d6ab0480d)

Cuando acabe de reiniciar nos saldrá este menú.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/e1805dbe-1f9b-44c9-a9f8-b96cc9d838ff)

Elegimos la opción 2, para añadir una ip.

Nos pide que interfaz queremos configurar, en este caso configuraremos la LAN.

Le pondremos una IP y la máscara de 24 bit.

En el siguiente campo lo dejamos vacio al igual que dejamos vacio la ipv6.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/0833e912-79e8-448e-b05c-e87d779b706b)

Le decimos que si queremos habilitar el DHCP y luego establecemos un rango para que les de a nuestras máquinas virtuales.

Y por último no queremos revertir de HTTPS a HTTP.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/df2385ba-04a2-41dd-a809-44a266badaef)

Vemos que nos da una URL.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/c020a306-abee-4a05-891c-1fd9ab3b6e0e)

Abrimos nuestra máquina virtual de Debian y comprobamos en configuración de red, que se le ha asignado una ip del rango anterior.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/29d5c311-4c04-44fa-85ad-26fe83e32f4b)

## CONFIGURACIÓN DE PFSENSE

Cuando entramos podemos comprobar que tiene acceso a internet, pero no puede resolver los DNS.

Para la configuración de Pfsense nos tendremos que meter en la url que antes nos dio la máquina virtual de pfsense.

El usuario por defecto es admin y la contraseña pfsense.

Tendremos que poner un nombre de hostname (pfSense.pfsenseasir.lab) y lo demas lo dejamos por defecto.

Ponemos la zona donde nos ubicamos.

Utilizaremos el modo DHCP, pero si fuese para una empresa lo mejor sería una ip estatica.

Pondremos una contraseña para adminitrador.

Y le damos a reiniciar para que se guarden los cambios. Cuando se reinicie nos saldrá una pantalla donde pondra 'finish', le damos.

Vamos a ver si el servidor pfsense puede resolver los dominios y tiene conectividad a internet.

Ahora vamos hacer que el cliente tenga conectividad con internet.
En interfaces de entrada seleccionamos LAN y Localhost. En la interfaz de salida seleccionamos WAN.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/2557fdc1-5d7c-49d9-8ffe-2276a555df14)

Seleccionamos la petición de redireccionamiento de DNS.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/b3d13095-93bb-4702-a005-76be05d8f0f8)

Seleccionamos las opciones para los registros DHCP.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/67a72427-c1c4-4897-a3eb-1f57aff09f01)

Guardamos y nos vamos a configuración avanzada.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/a812e4eb-6efd-42d9-9553-ca0a2ee0445b)

Seleccionamos la mayor capacidad para el caché dns.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/63960fcc-2e68-4d53-8701-0a5c82c11acd)

Y por últimos seleccionamos 1000 ordenadores para caché.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/2073b7f5-cef1-440a-a9b7-2f4057e5bd43)

Guardamos y aplicamos los cambios. 

Nos vamos al servidor DHCP y comprobamos el rango que pusimos anteriormente.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/0fca7c90-5113-401e-84ef-7eaed85bab61)

Habilitamos la opción para el formato de tiempo

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/9ab7f0aa-02be-4adb-816f-7e2523c7ec44)

Y para mostrar la gráfica de estadísticas.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/98e6c7f4-1c01-48cd-a115-68b01df670bd)

Nos vamos a las reglas de firewall.

Quitaremos la regla de ipv6.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/1a48d2a7-37fb-4c44-a451-813117d8f5fc)

Ahora haremos una limpieza en los registros y añadiremos varias opciones.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/c77ce189-9376-49aa-82f1-a4e5d3b19d26)

Seleccionamos la siguiente casilla para mostrar los registros de forma que esten los registros nuevos arribas.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/19c57237-d277-4169-816e-3f7ddbe7e95e)

El nº de entrada de registros lo ponemos en 30.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/4ab4ca45-def5-4fbe-bf4a-dd2e3afc1f3a)

Nos vamos de nuevo al firewall y editamos la regla de ipv4 habilitando la casilla para que nos muestre todos los registros de paquete de datos.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/a9b1555a-ef9b-4bf6-9c73-bfe8b7004e74)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/5eb04811-dbcc-4524-925d-d287fa3b7374)

Ahora comprobamos si tenemos ping a google, si la configuración es correcta hará ping.

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/7e3f157d-3af8-4ef5-937b-e2c2a9d7aaa5)

Para ver los registros:

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/d1743cb8-4b18-4439-99bd-4dd8b4b59d29)

![image](https://github.com/SeleneBP/VPN-y-Proxmox/assets/91204696/bc456e61-f5ab-4fa3-a449-ee57fcca50a8)

-----------------------------------------------------------------------------------------
#### LICENCIA

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia de Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">licencia de Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional</a>.
