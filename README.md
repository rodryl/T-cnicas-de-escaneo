# Técnicas de escaneo
Técnicas de escaneo descripción


## Escaneo Syn Stealth (Furtivo)

#### Comunicación:

Se envía un SYNC  
Se recibe un SYNC/ACK o un RST 
Y nunca se devuelve una respuesta; 

Por lo cual nunca termina de establecer el TCP 3 Way Handshake. Con esto se logra que los IDS y firewalls que cuentan con capacidad de logeo de eventos no registren la comunicación.

Nota: -packet-trace = muestra todas las banderas del protocolo TCP 
 
#### Test: 

Victima: 192.168.55.152 | Puerto: 23

-sS -p 23 -packet-trace 192.168.55.152

## Escaneo XMAS (Arbolito de navidad) 

Nota 1: Solo funciona si la implementación de de la pila de protocolos TCP/IP se ha desarrollado de acuerdo al RFC 793 

Nota 2: El escaneo XMAS NO funciona en los SO nuevos de Microsoft 

Nota 3: Un escaneo XMAS dirigido a sistemas Microsoft mostratá que todos los puertos están cerrados(aún si están abierto) 
 
#### Comunicación: 

Se envía un paquete con las flags FIN, URG, PUSH, +Puerto

Para cada puerto que se encuentre cerrado se recibirá una respuesta: Reset ACK
Para cada puerto que se encuentre abierto no se recibirá una respuesta: Nada

#### Test 

Víctima: 192.168.55.22 | Puerto:23 

-sX -p 23 192.168.55.22 
