### c) Permite que la máquina cortafuegos pueda navegar por https.

Para poder permitir que la máquina cortafuegos pueda navegar por https, deberemos añadir el siguiente comando con esta regla:

```sql
sudo nft add rule inet filter output tcp dport 443 ct state new,established accept
```

Cuando lo tengamos, pasamos a ver que se ha creado correctamente.

![FOTOS](img/5.png)

Para comprobar que funciona correctamente, le hecho una petición a wikipedia mediante este protocolo y vemos que funciona de manera correcta y adecuada:

![FOTOS](img/6.png)