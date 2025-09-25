# Cómo define Linux el tipo de archivo

En Linux (y en Unix en general), **el sistema de archivos no depende de extensiones** para saber qué tipo de archivo es.
### 🔹 Métodos principales:

1. **Metadatos del sistema de archivos (inodo):**  
    Cada archivo tiene un _inodo_ (Index Node) que indica si es:
    
    - archivo regular,
        
    - directorio,
        
    - enlace simbólico,
        
    - dispositivo, etc.
        
    
	Esto lo puedes ver con:

```bash
user@kali~ ls -l

-rw-r--r--  archivo.txt    → archivo regular
drwxr-xr-x  carpeta/       → directorio
lrwxrwxrwx  enlace -> destino → enlace simbólico
```
**Contenido del archivo (magic numbers):**  
Muchas veces Linux inspecciona los **primeros bytes del archivo** (cabecera mágica) para saber qué es.  
Ejemplo:

- Un **PNG** siempre empieza con: `89 50 4E 47`
    
- Un **PDF** siempre empieza con: `%PDF`
    
- Un ejecutable **ELF** comienza con: `7F 45 4C 46`
    

El comando `file` se basa en esto: revisa una base de datos de _magic numbers_ para identificar tipos.

## ¿Por qué no se usan extensiones?

- **Filosofía Unix**: "todo es un archivo", y el sistema no quiere depender de convenciones externas.
    
- **Mayor flexibilidad**: un archivo puede no tener extensión y aún así ser usado (ejemplo: ejecutables como `/bin/ls`).
    
- **Portabilidad**: los programas pueden reconocer archivos por su contenido sin importar el nombre.

# Determinando el tipo de archivos con "file"

En linux como ya mencionamos, muchas veces los archivos no tienen extension o pueden ser sustituidas sus extensiones, por lo cual es util asegurarnos del contenido de un archivo o que tipo de archivo es. Esto lo podemos hacer con `file`
`file [file name]`

```bash
file [opcciones] archivo.txt

file -i imagen.png
```
Ejemplo:
```bash
usuario@kali❯ file /etc/passwd
/etc/passwd: ASCII text

usuario@kali❯ file sin-extension
sin-extension: PDF document, version 1.7, 1 page(s)
```
### -i muestra su myme type
## 🔹 Ejemplos comunes

- **Archivos de texto**
    
    - `text/plain` → un `.txt`
        
    - `text/html` → una página web `.html`
        
    - `text/css` → hoja de estilos CSS
        
- **Archivos de imagen**
    
    - `image/png` → imagen PNG
        
    - `image/jpeg` → imagen JPG
        
    - `image/gif` → imagen GIF
        
- **Archivos de aplicación/binarios**
    
    - `application/pdf` → documento PDF
        
    - `application/zip` → archivo comprimido ZIP
        
    - `application/json` → datos JSON
**En la Web** → cuando un servidor envía un archivo, también envía su MIME type para que el navegador sepa qué hacer con él.  
Ejemplo:

- `Content-Type: text/html` → el navegador lo interpreta como página web.
    
- `Content-Type: application/pdf` → el navegador abre un visor de PDF.
# El comando `find`

##  ¿Qué hace?

Sirve para **buscar archivos y directorios** en el sistema de archivos según criterios como nombre, tipo, tamaño, permisos, usuario, etc.

A diferencia de `ls` (que solo lista), `find` **recorre recursivamente** los directorios.z
```bash
find [ruta] [condiciones] [acciones]
```

    ruta → dónde buscar (. para la carpeta actual, / para todo el sistema).

    condiciones → filtros (nombre, tamaño, usuario…).

    acciones → qué hacer con lo que encuentre (mostrar, borrar, ejecutar algo).
# Ver el contenido de un archivo con less 

# Entendiendo las carpetas del sistema linux, su jerarquia e impacto en el sistema
dasffdsa

# Links simbolicos

# Hard links

