### Túnel SSH

  - Túnel local   
  *"Mediante la conexiónpedimos permiso al servidor para ver el servicio"*   
  Cuando yo entre por mi localhost al puerto 8080, veré reflejado el servicio del puerto 80 de la segunda ip.
    ```sh
      ssh -l root 192.168.1.80 -L 8080: 192.168.2.1:80
    ```
  - Túnel remoto  
  *"Cuando me conecte, te habilitaré un puerto local para que haga tus consultas"*.  
  Cuando la ip .1.80 se conecte, se le dará acceso al servicio que corre en el puerto 22 pero el accederá por el purto 8080

    ```sh
      ssh -l root 192.168.1.80 -L 8080: 127.0.0.1:22
    ```
