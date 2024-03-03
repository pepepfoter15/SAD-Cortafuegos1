### i) Permite hacer conexiones ssh desde exterior a la LAN.

Cuando lo tengamos habilitamos las peticiones en el puerto 22 y las reglas dnat para hacer las peticiones con las siguientes reglas:

```sql
sudo nft add rule inet nat prerouting iifname "eth0" tcp dport 22 counter dnat ip to 192.168.100.10

sudo nft add rule inet filter forward iifname "eth0" oifname "eth1" ip daddr 192.168.100.0/24 tcp dport 22 ct state new,established counter accept
sudo nft add rule inet filter forward iifname "eth1" oifname "eth0" ip saddr 192.168.100.0/24 tcp sport 22 ct state established counter accept
```

Las reglas quedarán de la siguiente manera:

![FOTOS](img/16.png)

La prueba de que este cortafuegos funciona será haciendo desde mi host una petición a mi máquina LAN:

![FOTOS](img/17.png)