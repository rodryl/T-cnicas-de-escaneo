# Técnicas de escaneo
Técnicas de escaneo descripción


## Escaneo Syn Stealth 👋

Comunicación:

Se envía un SYNC  
Se recibe un SYNC/ACK o un RST 
Y nunca se devuelve una respuesta; 

Por lo cual nunca termina de establecer el TCP 3 Way Handshake. Con esto se logra que los IDS y firewalls que cuentan con capacidad de logeo de eventos no registren la comunicación.

Nota: -packet-trace = muestra todas las banderas del protocolo TCP 
 
#### Test: 

Victima: 192.168.55.152 Puerto: 23

-sS -p 23 -packet-trace 192.168.55.152


