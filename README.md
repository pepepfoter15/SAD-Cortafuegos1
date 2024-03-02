# SAD - Cortafuegos 1
Práctica de invididual de cortafuegos 1.

Realizada por Jose Carlos Rodríguez Cañas.

Realiza con NFTABLES el ejercicio de la página https://fp.josedomingo.org/seguridadgs/u03/perimetral_iptables.html documentando las pruebas de funcionamiento realizadas.

En mi caso la voy hacer en un escenario Vagrant ya que estoy más cómdodo utilizándolo. Teneís el archivo Vagrantfile en mi respositorio.

Debes añadir después las reglas necesarias para que se permitan las siguientes operaciones:

[a) Permite poder hacer conexiones ssh al exterior desde la máquina cortafuegos.](/Ejercicios/Ejercicioa.md)

[b) Permite hacer consultas DNS desde la máquina cortafuegos sólo al servidor 8.8.8.8. Comprueba que no puedes hacer un dig @1.1.1.1.](/Ejercicios/Ejerciciob.md)

[c) Permite que la máquina cortafuegos pueda navegar por https.](/Ejercicios/Ejercicioc.md)

[d) Los equipos de la red local deben poder tener conexión al exterior.](/Ejercicios/Ejerciciod.md)

[e) Permitimos el ssh desde el cortafuegos a la LAN.](/Ejercicios/Ejercicioe.md)

[f) Permitimos hacer ping desde la LAN a la máquina cortafuegos.](/Ejercicios/Ejerciciof.md)

[g) Permite realizar conexiones ssh desde los equipos de la LAN.](/Ejercicios/Ejerciciog.md)

[h) Instala un servidor de correos en la máquina de la LAN. Permite el acceso desde el exterior y desde el cortafuegos al servidor de correos. Para probarlo puedes ejecutar un telnet al puerto 25 tcp.](/Ejercicios/Ejercicioh.md)

[i) Permite hacer conexiones ssh desde exterior a la LAN.](/Ejercicios/Ejercicioi.md)

[j) Modifica la regla anterior, para que al acceder desde el exterior por ssh tengamos que conectar al puerto 2222, aunque el servidor ssh este configurado para acceder por el puerto 22.](/Ejercicios/Ejercicioj.md)

[k) Permite hacer consultas DNS desde la LAN sólo al servidor 8.8.8.8. Comprueba que no puedes hacer un dig @1.1.1.1.](/Ejercicios/Ejerciciok.md)

[l) Permite que los equipos de la LAN puedan navegar por internet, excepto a la página www.realbetisbalompie.es.](/Ejercicios/Ejerciciol.md)

![FOTO](Ejercicios/img/readme.jpg)