### h) Instala un servidor de correos en la máquina de la LAN. Permite el acceso desde el exterior y desde el cortafuegos al servidor de correos. Para probarlo puedes ejecutar un telnet al puerto 25 tcp.

Como nos pide que instalamos un servidor de correos en nuetra máquina LAN, lo que haremos será instalar postfix en dichha máquina primero de todo. Los comandos son los siguientes:

```sql
sudo apt update
sudo apt install postfix 
```

Cuando lo tengamos habilitamos las peticiones en el puerto 25 y las reglas dnat para hacer las peticiones con las siguientes reglas:

```sql
sudo nft add rule inet nat prerouting iifname "ens3" tcp dport 25 counter dnat ip to 192.168.100.10

sudo nft add rule inet filter forward iifname "ens3" oifname "ens4" ip daddr 192.168.100.0/24 tcp dport 25 ct state new,established counter accept
sudo nft add rule inet filter forward iifname "ens4" oifname "ens3" ip saddr 192.168.100.0/24 tcp sport 25 ct state established counter accept
```

Las reglas quedarán de la siguiente manera:

![FOTOS](img/14.png)

La prueba de que este cortafuegos funciona será haciendo desde mi host una petición a mi máquina LAN:

![FOTOS](img/15.png)