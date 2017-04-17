### Túnel SSH

  - Túnel local   
  Cuando me conecte a la primer ip (192.168.1.80) con el usuario root, levantaré mi puerto local (8080) y me darás acceso a tu servicio del puerto 22
    ```sh
      ssh -l root 192.168.1.80 -L 8080: 127.0.0.1:22
    ```
  - Túnel remoto   
  Cuando me conecte a la ip (192.168.1.80) con el usuario root, el servidor podrá accesar a mi servicio del puerto 22 por medio del puerto 8080.

    ```sh
      ssh -l root 192.168.1.80 -R 8080: 127.0.0.1:22
    ```
