# -Laboratorios-del-modulo-III-
COMANDO PRACTICA 3
Lista de comandos utilizados y válidos con su descripción para (configuración de red y SSH en centos):

ip a
  -> Muestra todas las interfaces de red y sus configuraciones IP.

sudo nano /etc/sysconfig/network-scripts/ifcfg-ens33
  -> Abre el archivo de configuración de red de la interfaz 'ens33' para editarlo con privilegios de superusuario.

sudo systemctl restart NetworkManager
  -> Reinicia el servicio de NetworkManager.

sudo systemctl start NetworkManager
  -> Inicia el servicio de NetworkManager si no está corriendo.

sudo systemctl restart network
  -> Reinicia el servicio de red clásico (no recomendado si se usa NetworkManager).

sudo systemctl start network
  -> Inicia el servicio de red clásico.

nmcli connection show
  -> Muestra las conexiones de red conocidas por NetworkManager.

nmcli device status
  -> Muestra el estado de los dispositivos de red.

rpm -q networkManager
  -> Verifica si el paquete 'networkManager' está instalado.

sudo yum install networkManager -y
  -> Instala NetworkManager y acepta automáticamente.

sudo systemctl enable --now NetworkManager
  -> Habilita e inicia NetworkManager al mismo tiempo.

ping google.com
  -> Verifica la conectividad a internet enviando paquetes ICMP a google.com.

ping 192.168.1.100
  -> Verifica conectividad con el host en esa IP local.

ping 192.168.0.108
  -> Prueba conexión con una IP específica en la red.

ping 192.168.0.102
  -> Prueba conexión con otra IP específica en la red.

ping -c 4 google.com
  -> Envía 4 paquetes ICMP a google.com para verificar conexión.

ip route | grep default
  -> Muestra la ruta por defecto (gateway).

cat /etc/resolv.conf
  -> Muestra los servidores DNS configurados.

ip route show
  -> Muestra la tabla completa de rutas IP.

sudo ip route add default via 192.168.1.1
  -> Agrega manualmente una ruta por defecto con esa puerta de enlace.

sudo mkdir -p /etc/sysconfig/network-scripts
  -> Crea el directorio si no existe (usado por configuraciones de red en CentOS/RHEL).

sudo nano /etc/sysconfig/network-scripts/ifcfg-enp0s3
  -> Edita el archivo de configuración de red para la interfaz enp0s3.

sudo nmcli con add type ethernet con-name "Conexion-cableada" ifname ens33
  -> Crea una nueva conexión ethernet llamada 'Conexion-cableada' para la interfaz 'ens33'.

nmtui
  -> Abre la interfaz de usuario en texto de NetworkManager.

sudo nmtui
  -> Abre nmtui con privilegios de superusuario.

systemctl status NetworkManager
  -> Muestra el estado actual del servicio NetworkManager.

sudo systemctl enable NetworkManager
  -> Habilita NetworkManager para que se inicie al arrancar el sistema.

ip addr show
  -> Muestra la configuración IP de todas las interfaces de red.

sudo yum install -y openssh-server
  -> Instala el servidor OpenSSH.

sudo systemctl start sshd
  -> Inicia el servicio SSH.

sudo systemctl enable sshd
  -> Habilita el servicio SSH para que arranque automáticamente.

sudo systemctl status sshd
  -> Muestra el estado del servicio SSH.

sudo firewall-cmd --permanent --add-service=ssh
  -> Permite el servicio SSH permanentemente en el firewall.

sudo firewall-cmd --reload
  -> Recarga la configuración del firewall para aplicar cambios.

mkdir -p ~/.ssh
  -> Crea el directorio '.ssh' en el home del usuario si no existe.

chmod 700 ~/.ssh
  -> Establece permisos seguros para el directorio '.ssh'.

nano ~/.ssh/authorized_keys
  -> Abre el archivo para agregar claves públicas autorizadas para SSH.

chmod 600 ~/.ssh/authorized_keys
  -> Establece permisos seguros para el archivo de claves autorizadas.

pwd
  -> Muestra la ruta del directorio actual.
