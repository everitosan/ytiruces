## TOP
  Muestra los procesos que actualmene están corriendo en una tabla que se actualiza en tiempo real.

  ```sh
  top
  ```
  Se puede ordenar mediante la tecla "o", y especificanco el campo de referencia para el orden.

## PS
  Enlista todos los procesos que se están ejecutando en ese momento.  
  ```sh
    ps -wA
  ```
## KILL
  Termina el proceso indicado por el pid
  ```sh
    kill [-9 , -12 , -15] pid
  ```
  **-9** Finalizar proceso (agresivo)  
  **-15** Finaliza tarea del proceso y termina el mismo (termino medio)  
  **-2** Similar a cerar el programa tranquilamente

## GREP  
  Buscar cadenas de texos en los archivos.  
  - Busca la cadena de texto "mundo" en el archivo hola.txt
  ```sh
    cat hola.txt | grep mundo
  ```
  - Busca una cadena de texto en todos los archivos dentro del directorio actual
  ```sh
    grep -r . -e mundo$
  ```
  **$** en expresión regular funciona para indicar un final o salto de línea    
  **^** en expresión regular funciona para indicar un inicio de línea

## FIND
  Buscar archivos  
  - Buscar Todos los archivos dentro del directrio Documentos con extensión txt que sean del tipo file  

  ```sh
    find ~/Documents -name "*.txt" -type f
  ```  

  - Buscar y ejecutar comands sobre archivos encontrados.  
  En el ejemplo compiará los archivos con extensión txt y los copiará dentro de la carpeta txt del directorio actual.

  ```sh
    find ~/Documents -name "*.txt" -type f -exec cp {} ./txt/ \;
  ```

## CURL  
  Peiciones por inernet

  ```sh
    curl -o google.html https://www.google.com
  ```
