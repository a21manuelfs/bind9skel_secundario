## 1.3 INSTALACION DE ZONAS SECUNDARIAS. 

### 1- Tomaremos a máquina darthsidious, e configuraremola para ser servidor secundario, 
### tanto da zona primaria de resolución directa como de resolución inversa. 
### Captura os ficheiros de configuración en ambalas dúas máquinas. 
### Fai unha captura onde se vexa o reinicio da máquina darthsidious, 
### no que se vexa no log dos dous equipos e que se fixo a transferencia de zona.

### FICHEROS DE CONFIGURACION SERVIDOR DNS MAESTRO

#### CONFIGURACION NAMED.CONF.LOCAL DEL DNS MAESTRO.
![config_primario](imagenes/Named.conf.local_serv_primario.png)
#### CONFIGURACION ZONA DIRECTA DEL DNS MAESTRO.
![zona_primaria](imagenes/ZonaDirecta_primario.png)
#### CONFIGURACION ZONA SECUNDARIA DEL DNS MAESTRO.
![zona_secundaria](imagenes/ZonaSecundaria_primario.png)

### FICHEROS DE CONFIGURACION SERVIDOR DNS ESCLAVO.

#### CONFIGURACION NAMED.CONF.LOCAL DEL DNS ESCLAVO.
![config_esclavo](imagenes/named.conf.local(esclavo).png)
#### CONFIGURACION ZONA DIRECTA DEL DNS ESCLAVO .
![zona_principal_esclavo](imagenes/db.starwars.lan(esclavo).png)
#### CONFIGURACION ZONA SECUNDARIA DEL DNS ESCLAVO.
![zona_secundaria_esclavo](imagenes/db.192.168.20(esclavo).png)

### CAPTURAS DE TRANSFERENCIA DE ZONAS
#### PRIMER REINICIO TRAS EL CAMBIO DE SERIAL (SE TRANSFIEREN LAS ZONAS)
![primer_reinicio](imagenes/PrimerReinicio(serial_change).png)

#### SI SE REINICIA EL SECUNDARIO NO SE TRANSFIERE NADA POR ESTAR ACTUALIZADO.
![segundo_reinicio](imagenes/Segundo_reinicio(sin_cambios).png)

#### PROBANDO QUE LAS ZONAS SE TRANSFIEREN CORRECTAMENTE MANUALMENTE (POR COMANDO)
![transferencia_manual](imagenes/Tranferencia_zonas(manual).png)

### 2- Engade un rexistro tipo A (Chewbacca 192.168.0.28) na zona de resolución directa e tamén na de resolución inversa.  
### Fai unha captura no momento do reinicio do equipo darthvader, no que se vexa o log dos dous equipos e que se amose que se fixo a transferencia de zona. Adxunta tamén unha captura do ficheiro de zona no servidor secundario.

#### AÑADIENDO NUEVO REGISTRO ZONA DIRECTA CHEWBACCA
![nuevo_reg_pri](imagenes/new_reg_pri_zone.png)

#### AÑADIENDO NUEVO REGISTRO ZONA INVERSA R2D2 
![nuevo_reg_sec](imagenes/new_reg_sec_zone.png)

#### CAPTURAS DE TRANSFERENCIA DE ZONAS AL REINICIAR
![transfer_zones](imagenes/transfer_zones(new).png)

#### TRANSFERENCIA DE ZONAS MANUALMENTE
##### ZONA DIRECTA
![trans_zonaDir](imagenes/zonaDirecta_tranferenciaManual.png)

##### ZONA INVERSA
![trans_zonaInv](imagenes/zonaInversa_transferenciaManual.png)

### 3- Comproba que o servidor secundario pode resolver ese nome.
![resolv_chewbacca](imagenes/resolve_chewbacca.png)

### 4- Fai os cambios necesarios para que as trasferencias se fagan de forma segura empregando chaves. 
### Repite as capturas e vídeos do punto 2, engadindo o rexistro r2d2 (192.168.0.29)

#### KEY EN EL MAESTRO
![key_maestro](imagenes/key_master.png)

#### KEY EN EL ESCLAVO
![key_esclavo](imagenes/key_esclavo.png)

#### TRANSFERENCIA DE ZONAS CON CLAVE.
![trans_claves](imagenes/transfer_zones_claves.png)

#### R2D2 EN ZONA DIRECTA
![r2d2_directa](imagenes\r2d2_directa.png)

#### R2D2 EN ZONA INVERSA
[r2d2_inversa](imagenes\r2d2_inversa.png)
