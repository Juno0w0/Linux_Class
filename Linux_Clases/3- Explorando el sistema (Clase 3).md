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

Porque es util esto? Por que Linux no toma en cuenta 


# Ver el contenido de un archivo desde terminal 

# Entendiendo las carpetas del sistema linux, su jerarquia e impacto en el sistema
dasffdsa

# Links simbolicos

# Hard links

