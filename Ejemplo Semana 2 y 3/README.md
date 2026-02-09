# Guía Práctica: Introducción a Packet Tracer

**Curso:** Redes de Computadoras 1
**Objetivo:** Comprender la jerarquía de capas, el cableado correcto y realizar la primera prueba de conectividad (Ping).

---

## El Entorno Visual (Lado Izquierdo)

En esta sección hemos dibujado una topología para entender cómo se organizan los dispositivos según el **Modelo OSI**.

### Herramientas de Diseño

Para que sus topologías se vean profesionales, utilizamos la barra de herramientas superior:

* **Formas (Rectángulos/Círculos):** Sirven para agrupar áreas lógicas (como verán en los cuadros Verde y Celeste).
* *Tip:* Pueden cambiar el color de fondo seleccionando "Fill Color".


* **Notas (Icono de hoja):** Permiten escribir texto libre en el área de trabajo.
* *Tip:* Packet Tracer acepta etiquetas básicas de HTML. Prueben escribir `<b>Titulo en Negrita</b>` o `<font color="red">Texto Rojo</font>`.



### Reglas de Cableado

Observen las conexiones en el diagrama:

| Dispositivos a conectar | Tipo de Dispositivo | Cable a usar | Aspecto visual |
| --- | --- | --- | --- |
| **Router ↔ Router** | Iguales (Capa 3) | **Cruzado** | Línea punteada |
| **Switch ↔ Switch** | Iguales (Capa 2) | **Cruzado** | Línea punteada |
| **Router ↔ Switch** | Diferentes | **Directo** | Línea sólida ──── |
| **PC ↔ Switch** | Diferentes | **Directo** | Línea sólida ──── |

> **Nota:** En el diagrama de la izquierda, los Routers y Switches **NO** tienen configuración interna todavía. Son solo para visualizar la estructura física y el tipo de cable.

---

## Ejercicio Práctico

Ahora vamos a configurar una red pequeña funcional entre una **PC** y una **Laptop**.

### Paso 1: Conexión Física

1. Arrastra una **PC** y una **Laptop** al área de trabajo.
2. **El Cable:** Como ambos dispositivos son Hosts finales (Capa 3), se consideran "iguales".
* Selecciona el rayo (Conexiones) y busca el **Cable Cruzado** (Copper Cross-Over).
* Conecta del puerto **FastEthernet0** de la PC al **FastEthernet0** de la Laptop.



### Paso 2: Configuración de Direcciones IP

Para que se "pueda intentar el ping", deben estar en la misma red lógica. Usaremos la red `192.168.1.0`.

**Configurar la PC (PC-PT):**

1. Haz clic sobre la PC.
2. Ve a la pestaña **Desktop** > **IP Configuration**.
3. Ingresa estos datos:
* **IPv4 Address:** `192.168.1.2`
* **Subnet Mask:** `255.255.255.0` (Aparece sola al dar clic).
* *Default Gateway:* Déjalo en `0.0.0.0` (No es necesario porque no saldremos a internet).



**Configurar la Laptop (Laptop-PT):**

1. Haz clic sobre la Laptop.
2. Ve a la pestaña **Desktop** > **IP Configuration**.
3. Ingresa estos datos:
* **IPv4 Address:** `192.168.1.3`
* **Subnet Mask:** `255.255.255.0`



---

## Hacer PING

Vamos a verificar que la comunicación fluye correctamente.

1. Abre de nuevo la **PC (PC-PT)**.
2. Ve a la pestaña **Desktop** y busca **Command Prompt** (Símbolo del sistema).
3. Escribe el siguiente comando y presiona `Enter`:
```bash
ping 192.168.1.3

```