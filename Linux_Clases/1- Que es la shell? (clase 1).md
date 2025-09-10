
#  🐧  Introducción a Linux y primeros pasos en la terminal 🐧

### - **1969** → Nace UNIX (en AT&T Bell Labs).

Unix es un sistema operativo desarrollado en los anios 60 por los AT&T BELL LABS, con una filosofia clara: simple, modular y multitarea.
Sirvio como base para muchos sistemas operativos modernos: Linux, macOS, Solaris, etc.
Esta escrito en C
### - **1983** → Proyecto GNU de Richard Stallman (crear un sistema operativo libre).

Fue un proyecto que tenia como objetivo crear un sistema operativo **libre, tipo UNIX**  pero sin restricciones privativas **(GNU's Not Unix)** 
Tenia pensado contar con 4 libertades basicas
- Usar el programa como quieran.

- Estudiar cómo funciona (requiere acceso al código fuente).

- Modificarlo y adaptarlo a sus necesidades.

- Compartir copias, con o sin modificaciones.

Lamentablemente no pudieron hacer un kernel en ese momento  😿 solo las herramientass basicas de un OS que mas adelante pasarian a ser parte de LINUX 

### - **1991** → Linus Torvalds crea el **kernel de Linux** como un hobby universitario.

En 1991, **Linus Torvalds** creó el **kernel de Linux**.
Cuando se juntó el kernel de Linux con las herramientas de GNU, se obtuvo un sistema operativo funcional: **GNU/Linux**.
Por eso técnicamente, el sistema que usamos (Ubuntu, Debian, Fedora, etc.) se debería llamar **GNU/Linux**, aunque comúnmente lo simplificamos a **Linux**.

Lo que usamos como "Linux" en realidad son **distribuciones** (ej. Ubuntu, Debian, Fedora), que combinan:

- Kernel de Linux.

- Herramientas GNU.

- Programas adicionales.

### - **Hoy** → Linux se usa en servidores, supercomputadoras, móviles (Android), IoT, seguridad, etc.

- **Software libre** → cualquiera puede usarlo, modificarlo y compartirlo.

- **Estabilidad y seguridad** → muy usado en servidores y entornos críticos.

- **Escalabilidad** → funciona en un reloj inteligente o en una supercomputadora.

- **Personalización** → puedes adaptar todo (distinto a Windows/macOS que son cerrados).

## Que es la shell? 

La **shell** es un **intérprete de comandos**: un programa que actúa como intermediario entre el usuario y el sistema operativo.

Cuando escribes un comando en la terminal (por ejemplo, `ls` para listar archivos), la **shell** se encarga de:

1. **Leer** lo que escribiste.
2. **Interpretarlo** (entender qué comando es y con qué parámetros).
3. **Ejecutarlo** comunicándose con el kernel del sistema operativo.
4. **Mostrarte el resultado** en pantalla.
# Emuladores de Terminal 🕹️

Existen diferentes tipos de **shells** en sistemas tipo UNIX/Linux, algunos ejemplos son:

- **sh** (Bourne Shell, la original).
- **bash** (Bourne Again Shell, la más común en Linux).
- **zsh** (Z Shell, muy usada por su personalización).
- **fish** (Friendly Interactive Shell, más interactiva y moderna).

#### **1. sh (Bourne Shell)**

- **La original**, creada en los años 70 en UNIX.
- Muy básica: soporta scripts y ejecución de comandos, pero sin características modernas.
- Se usa mucho aún en **scripts de compatibilidad** porque está presente en casi todos los sistemas Unix/Linux.
- No tiene autocompletado avanzado ni personalización.  
    ✅ Ventaja: máxima portabilidad.  
    ❌ Desventaja: muy limitada para el uso interactivo.
#### **2. bash (Bourne Again Shell)**

-  **La más común en Linux** (de hecho, suele ser la shell por defecto en la mayoría de distribuciones).
- Extiende a `sh` con muchas mejoras:
    - Historial de comandos (`↑ ↓`).
    - Autocompletado básico.
    - Variables y arrays más avanzados.
    - Scripts más potentes y fáciles de escribir.
- Compatible con `sh`, así que puede ejecutar la mayoría de scripts antiguos.  
    ✅ Ventaja: equilibrada, estándar en Linux.  
    ❌ Desventaja: menos personalizable que `zsh` y menos interactiva que `fish`.

#### **3. zsh (Z Shell)**

-  Más moderna que `bash`, con **alto nivel de personalización**.
- Muy popular en usuarios avanzados y en macOS (desde Catalina es la shell por defecto).
- Funciones destacadas:
    - **Autocompletado avanzado** (te sugiere comandos, opciones y rutas).
    - **Corrección automática** de errores tipográficos (`grpe` → `grep`).
    - **Temas y plugins** fáciles de instalar (ej. _oh-my-zsh_).
- Ideal para quien usa mucho la terminal y quiere eficiencia + estilo.  
    ✅ Ventaja: potente y personalizable.  
    ❌ Desventaja: necesita configuración para sacarle el máximo provecho.

####  **4. fish (Friendly Interactive Shell)**

- Diseñada para ser **amigable desde el inicio**.
- No intenta ser 100% compatible con `sh` o `bash`, sino **más interactiva**.
- Funciones destacadas:
    - **Autocompletado inteligente** basado en historial y documentación.
    - **Coloreado automático** de comandos y sintaxis.
    - Configuración más simple, con un **panel web** para gestionar ajustes.
- Ideal para usuarios que no quieren complicarse con configuraciones.  
    ✅ Ventaja: usable y moderno "out of the box".  
    ❌ Desventaja: menos portable para scripting, ya que no es totalmente compatible con bash/sh.

#### Como saber que tipo de shell tengo yo?
`echo $SHELL`
`echo $0`
`cat /etc/shells`
# Haciendo tu primer Keystrokes y comandos basicos

el prompt shell $(user) #(root o su)

 `date`
 `pwd`
 `ls`
 `cd`
 `cat`
 `mkdir`
 `cal`

#### Command History
El historial de comandos de linux y se usa con las flechas arriba y abajo
#### Terminando una sesion de shell
exit


 