
## NETCAT  
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

    *La Bifurcación funciona de izquierda a derecha, toda salida se interpreta como entrada del siguiente bloque*

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

    -SERVER Cuando alguien se conecte ejecutará bash
    ```sh
      nc -lvp 8080 -e /bin/bash
    ```

    --CLIENT El cliente podrá ejecutar comandos en el servidor
    ```sh
      nc 127.0.0.1 8080
    ```
    #### TELNET INVERSO
    --SERVER Solo escuchará en el puerto 8080 y podrá ejecutar bash cuando un cliene se conecte
    ```sh
      nc -lvp 8080
    ```
    --CLIENT Al conectarse el cliente, el servidor podrá ejecutar comandos bash.
    ```sh
      nc 127.0.0.1 -e /bin/bash
    ```
    #### Bifurcación entre túneles de puertos
    --SERVER escucha en el puerto 8080, pasando la salida a bash qu le pasa el resultado al puerto 9090
    ```sh
      nc -lvp 8080 | /bin/bash | nc -lvp 9090
    ```
    --CLIENT1 se conecta al puerto 8080, los comndo que envie serán ejecutados por el bash del server y mostrados por el puerto 9090
    ```sh
      nc 127.0.0.1 8080
    ```

    --CLIENT2 se conectará al puerto 9090. Toda la información enviada será intepretada solo como texto, pero la salida por el mismo será la salida de la ejecución del CLIENE1
    ```sh
      nc -lvp 127.0.0.1 9090
    ```
## CRYPTCAT
  Es una alternativa a nectat con una capa ssl que a diferencia de **netcat**, no envía la información en texto plano.
