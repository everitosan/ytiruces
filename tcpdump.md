## TCPDUMP
Analiza paquetes por medio de un interfaz en línea de comandos. Alterniativa de terminal a WireShark

Por defecto analizará la interfaz eth0

```sh
  tcpdump
```  

Se puede customizar el grado de verbose con el flag **-v** ó **-vvv** y asignar la interfaz por medio del flag **-i**

```sh
  tcpdump -vv -i lo
```

Podemos filtrar por host con el flag **host**.  
El flag **-nn** dejamos de mostrar la resolución del dominio.
```sh
  tcpdump -nn -i eth0 host 192.124.249.8
```
Para exportar los paquetes caprutados podemos usar el flag **-w**

```sh
  tcpdump -nn -vvv -i eth0 host 192.124.249.8 -w prueba.pcap
```

Podemos leer también un archivo con auda del flag **-r**
```sh
  tcpdump -r prueba.pcap
```
Para ver las tramas de paquetes en raw, usamos el flag **-XX**
```sh
  tcpdump -XX -i eth0
```
