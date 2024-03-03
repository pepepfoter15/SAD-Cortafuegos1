### g) Permite realizar conexiones ssh desde los equipos de la LAN.

Para poder ssh a alguna máquina del mismo exterior (por ejemplo en mi caso he hecho que funcione el ssh a las máquinas de las red de openstack), tendremos que añadir las siguientes reglas:

```sql
sudo nft add rule inet filter forward iifname "ens4" oifname "ens3" ip saddr 192.168.100.0/24 tcp dport 22 counter accept
sudo nft add rule inet filter forward iifname "ens3" oifname "ens4" ip saddr 172.22.0.0/16 ct state established,related counter accept
```

Las reglas quedarán de la siguiente manera:

![FOTOS](img/12.png)

La prueba de que este cortafuegos funciona accediendo a mi máquina de odin:

![FOTOS](img/13.png)