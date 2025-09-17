# Entendiendo el sistema de archivos

A la vez del "typing" dentro de linux necesitamos entender como **navergar** en el sistema linux
La jerarquia de archivos de linux es parecida a windows, donde podemos encontrar carpetas con archivos y otras carpetas dentro. si necesitamos conocer la ruta actual de una carpeta donde estemos podemos usar el comando `pwd` asi podemos ver la jerarquia de directorios donde nos encontramos.
El primer folder del sistema donde se encuentra todo es el *root directory* , a diferencia de windows que tiene un sistema de arbol para cada dispositivo de almacenamiento linux monta todo el sistema y los dispositivos de almacenamiento sobre el ROOT " **/** " y el administrador de sistema puede decidir la jerarquia y posicion de estos sistemas de almacenamiento 

![](https://linuxhandbook.com/content/images/2020/06/linux-directory-structure.png)

### El "current working directory"

`PWD` (print working directory)
Con este comando podemos ver el CWD y asi saber en donde estamos en todo momento

#### 1- Ejercicio
	Sin moverte del directorio actual vas a listar los archivos binarios de la carpeta bin, luego escoger uno y abrir su contenido para ver el texto dentro de ese binario

Siempre que entramos en nuestro sistema por defecto nuestro CWD es el directorio "Home"
# Formas de listar el contenido de un directorio

Podemos usar el comando **ls**
`ls [opciones] [ruta]`
ls -l /home/sheepsstealer/Downloads
Tambien podemos mostrar varios directorios a la vez
`ls ~ /etc`
Tambien podemos encontrar dinstintas formas de hacer lo mismo con ls y otros comandos ya que el proyecto GNU contiene banderas que pueden ir precedidas de -- con palabras largas, por ejemplo --reverse
ls -ltr
ls -lt --reverse

## 🔹 Banderas más comunes de `ls`

| Bandera | Significado                                                                    | Ejemplo           | Resultado                                        |
| ------- | ------------------------------------------------------------------------------ | ----------------- | ------------------------------------------------ |
| `ls`    | Lista archivos y carpetas en el directorio actual                              | `ls`              | `archivo.txt carpeta1 script.sh`                 |
| `-l`    | Lista en **formato largo**: permisos, propietario, tamaño, fecha               | `ls -l`           | `-rw-r--r-- 1 user user 1234 Sep 15 archivo.txt` |
| `-a`    | Muestra **todos los archivos**, incluso los ocultos (los que empiezan con `.`) | `ls -a`           | `.bashrc .config archivo.txt carpeta1`           |
| `-h`    | Con `-l`, muestra tamaños en formato **legible** (K, M, G)                     | `ls -lh`          | `-rw-r--r-- 1 user user 12K Sep 15 archivo.txt`  |
| `-t`    | Ordena por **fecha de modificación** (recientes primero)                       | `ls -lt`          | Muestra primero los archivos más nuevos          |
| `-r`    | Invierte el orden (útil con `-t` o `-l`)                                       | `ls -ltr`         | Muestra los más antiguos primero                 |
| `-R`    | Lista de forma **recursiva** subdirectorios                                    | `ls -R`           | Expande el contenido de las carpetas             |
| `-d`    | Muestra la **carpeta en sí**, no su contenido                                  | `ls -d carpeta1/` | `carpeta1/`                                      |
# Cambiando el CWD

Puedes cambiar de CWD con el comando `cd` seguido del *pathname* de a donde queremos ir, podemos especificar el *pathname* de dos formas: como *rutas absolutas* o *rutas relativas*

## 🔹 Casos y usos más comunes de `cd`

| Comando                | Explicación                                                          | Ejemplo                                                              |
| ---------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `cd`                   | Sin argumentos → te lleva a tu **directorio home** (`/home/usuario`) | `cd`                                                                 |
| `cd /ruta/absoluta`    | Va a un directorio usando la ruta completa                           | `cd /etc`                                                            |
| `cd nombre_directorio` | Usa ruta **relativa** desde donde estés                              | `cd Documentos`                                                      |
| `cd ..`                | Sube **un nivel** en la jerarquía de directorios                     | Si estás en `/home/user/Documentos`, con `cd ..` vas a `/home/user`  |
| `cd -`                 | Regresa al **último directorio** en el que estabas                   | Si estabas en `/etc` y luego en `/home`, con `cd -` vuelves a `/etc` |
| `cd ~`                 | Va directo al **home** del usuario actual                            | `cd ~`                                                               |
| `cd ~/ruta`            | Desde home, entra a una subcarpeta                                   | `cd ~/Descargas`                                                     |
### Rutas absolutas
Las rutas absolutas son aquellas que inician desde el *root directory* / y van hasta el directorio que queremos visualizar o trabjar
### Rutas relativas
Asi como las rutas absolutas vienen desde el root hasta el destino, las relativas van desde el CWD hasta el destino, para hacer esto posible tenemos dos notaciones especiales para representar la posicion en el sistema de archivos. El . (dot) y el .. (dot dot) 
El . se refiere al directorio actual, y el .. al directorio padre de donde nos encontramos.

### Que es mejor ocupar? Lo que nos permita typear menos!! :D 

# Fun Facts 
* Los archivos y dirctorios en linux que tengan un . al principio del nombre (.ejemplo) apareceran ocultos, lo que quiere decir que ls no los mostrara a no ser que ocupemos `ls -a`
* Los filenames en linux son case sentitive, o sea que file1 y File1 son cosas distintas
* Linux no tiene el concepto de "Extension de archivo" como otros sistemas, de hecho ningun sistema de unix lo tiene XD por lo que no utilizan extensiones. 
  Aun asi, sirve nombrar al archivo con extencion porque otros programas si validan la extencion. 
# Explicacion de salida ls -l

Cuando ocupes el comando ls -l veras la salida larga 
drwxrwxr-x sheepsstealer sheepsstealer 4.0 KB Tue Sep 16 21:15:39 2025  drive
.rw-rw-r-- sheepsstealer sheepsstealer 468 B  Wed Jun 18 15:14:26 2025  pythoncode.py

| CAMPO                    |                                                                                                                                                                                                                                                                                                                                                               SIGNIFICADO                                                                                                                                                                                                                                                                                                                                                               |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **d**rwxrwxr-x           | El primer caracter indica el tipo de archivo, por ejemplo la d indica *directorio* un '-' o '.' indicaria fichero regular, tambien puede tener otras letras como l o b que indican archivos especiales. Los otros 9 caracteres se dividen en grupos de 3 "rwx" y pertenecen a "Owner/Group/Others". <br>Los Owners son quienes crean el archivo, si sheepsstealer crea un archivo el es el **Owner**<br>El Group es el grupo al que pertenece el archivo, todos los archivos pertenecen a un grupo y todos los miembros del grupo comparten los permisos. Por ejemplo, si yo "sheepsstealer" creara un archivo cualquier otro usuario que este en mi grupo puede tener los mismos permisos que yo<br>Other incluye a todos los demas XD |
| 1                        |                                                                                                                                                                                                                                                                                                                                      Numero de hard links que apuntan a este archivo o directorio                                                                                                                                                                                                                                                                                                                                       |
| sheepsstealer            |                                                                                                                                                                                                                                                                                                                                                 El username del propietario del archivo                                                                                                                                                                                                                                                                                                                                                 |
| sheepsstealer            |                                                                                                                                                                                                                                                                                                                                               el nombre del grupo propietario del archivo                                                                                                                                                                                                                                                                                                                                               |
| 4.0KB                    |                                                                                                                                                                                                                                                                                                                                                            size del archivo                                                                                                                                                                                                                                                                                                                                                             |
| Tue Sep 16 21:15:39 2025 |                                                                                                                                                                                                                                                                                                                                               fecha de la ultima modificacion del archivo                                                                                                                                                                                                                                                                                                                                               |
| drive                    |                                                                                                                                                                                                                                                                                                                                                           nombre del archivo                                                                                                                                                                                                                                                                                                                                                            |


