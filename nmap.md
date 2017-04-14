## NMAP

Herramienta de escaneo de red.

  - ### Exlporar la red
    Podemos escanear la red para encontrar los dispositivos conectados y su ip por medio de pings indicando la subred.  

    Según la máscara de red 255.255.255.0, 24 es igual al número de bits que se usan en la máscara.

    ```sh
      nmap -sP 192.168.1.0/24
    ```
  - ### Obtener el sistema operativo
    Conlleva ciero grado de falsos positivos sobre cierta ip en específico.
    ```sh
      nmap -O 192.168.1.60
    ```
  - ### Obtener la versión de puertos abiertos
    Según sea el caso
    ```sh
      nmap -sV 192.168.1.60
    ```
  - ### Flag -T4
    Indica la fuerza con la que se ejecuta
  - ### Flag -traceroute 
    Nos marca los saltos para llegar al objetivo
