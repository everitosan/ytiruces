
##NETCAT
Nos permite abrir puertos y hacer conexiones por medio de él.

 - Modo directo (Abrir un puerto y conectarse at ravés de él)  
    ### Chat
    -SERVER Escucha por el puerto 8080
     ```sh
      nc -l -v -p 8080
      ```
    -CLIENT Conecta al Servidor
    ```sh
      nc 127.0.0.1 8080
    ```
    ### UDP
    -SERVER Escucha pr el puerto 8080 pero con conexión udp
    ```sh
      nc -l -u -vv -p 8080
    ```
    -CLIENT Conecta al servidor
    ```sh
      nc -u 127.0.0.1 8080
    ```
    ### Bifurcación
    Puede recibir los archivos pero la conexión seguirá en escucha por lo que hay que realizar cálculos para terminar la misma una vez se halla copiao el archivo.  

    -SERVER Escucha por puerto 8080 y guarda en archivo
    ```sh
      nc -lvp 8080 > archivo
    ```
    -CLIENT Manda archivo ejemplo.txt al server
    ```sh
      nc 127.0.0.1 8080 < ejemplo.txt
    ```
    ### Acceso remoto
    #### TELNET

    -SERVER
    ```sh
      nc -lvp 8080 -e /bin/bash
    ```

    --CLIENT
    ```sh
      nc 127.0.0.1 8080
    ```
