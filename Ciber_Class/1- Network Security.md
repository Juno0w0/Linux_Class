La **Network Security** (_Seguridad de RED_ )es como la seguridad de una casa, asi como tienes que cuidar la puerta y las ventanas tienes que cuidar la seguridad de los dispositivos de las amenzas. La seguridad de Red protege a los dispositivos y los datos en tu red de los hackers externos y las amenazas internas.
 ![imagen](https://www.mydraw.com/NIMG.axd?i=Templates/NetworkDiagram/CiscoNetworkSecurityDiagram/CiscoNetworkSecurityDiagram.png) 
 ### **Elementos** 
_Firewalls:_ Actuan como barreras entre los agentes externos y los sistemas internos controlando quien entra y  sale de la red asi como filtrando el trafico de red segun reglas predeterminadas
filtra paquetes basándose en reglas predefinidas (direcciones IP, puertos, protocolos, etc.).
**Acción:** **bloquea o permite** el tráfico, nada más
	Ejemplo: Imagina una caseta de peaje, solo deja pasar a conductores que tengan el TAG o su recibo de pago a la mano, si no, los filtrara

_IDS/IPS:_  Monitorea el trafico de red y toma acciones automatizadas en caso de detectar actividades sospechosas. analiza patrones, firmas de ataques conocidos o comportamientos anómalos en la red.
**IDS:** **Acción:** **solo alerta**, no bloquea
	Ejemplo: Detecta que un atacante está haciendo un escaneo de puertos, y genera una alerta al administrador.
**IPS:** - **Acción:** **alerta + bloquea/mitiga**.
    **Ejemplo:** Detecta un exploit en un paquete y lo descarta antes de que llegue al servidor.

#### Diferencia resumida

| Componente   | Función                            | Acción                                            |
| ------------ | ---------------------------------- | ------------------------------------------------- |
| **Firewall** | Control de acceso (qué entra/sale) | Permitir o bloquear tráfico según reglas simples  |
| **IDS**      | Detección de ataques               | Generar alertas, sin intervenir                   |
| **IPS**      | Detección + prevención             | Alertar y bloquear/mitigar ataques en tiempo real |
_Virtual Private Networks (`VPNs`):_  Es una tecnologia que crea un "tunel seguro" para la conexion entre dos dispositivos en una red
1. **Cifrado:** todos los datos que envías/recibes viajan encriptados, como si fueran en un canal secreto.
2. **Anonimato relativo:** oculta tu dirección IP real y la reemplaza con la del servidor VPN.
3. **Acceso remoto seguro:** permite conectarte a una red privada (por ejemplo, la de tu empresa) como si estuvieras físicamente ahí.
4. **Evitar censura o bloqueos:** puedes acceder a sitios o servicios restringidos por ubicación.
#### ¿Cómo funciona?

1. Te conectas a un **servidor VPN** usando un software cliente.
2. El cliente crea un **túnel cifrado** con el servidor.
3. Todo tu tráfico pasa primero por el servidor VPN y luego sale a internet.

_Tecnologias de Cifrado y Encriptacion:_ Son tecnologias que cambian el valor de los datos que viajan por la red para evitar que puedan ser leidos por alguien si llega a interceptarlos.
Durante la comunicacion cliente-servidor se crean tuneles de comunicacion que comparten paquetes que contienen informacion, si alguien los intercepta capta esos paquetes y podria interpretar su contenido con herramientas
Por eso generamos tuneles con tecnologia de cifrado, si alguien intercepta los paquetes vera caracteres extranios que no podria interpretar. 
