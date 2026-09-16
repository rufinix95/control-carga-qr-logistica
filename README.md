# 🚚 Control de Carga QR — Trazabilidad Digital de Expediciones

Sistema web diseñado para digitalizar y simplificar el control de carga de pedidos en entornos logísticos e industriales mediante códigos QR.

El proyecto permite transformar un proceso tradicional basado en documentación, comprobaciones manuales y comunicación entre departamentos en un flujo digital organizado por rutas, expediciones y estados.

> 🔒 El código fuente se mantiene privado debido a que el proyecto reproduce lógica de negocio y flujos asociados a un entorno industrial real.  
> Este repositorio funciona como documentación técnica y demostración del proyecto.

---

## 🎯 Problema que intenta resolver

En un proceso de carga tradicional, comprobar qué pedidos pertenecen a cada ruta y verificar que todo el material ha sido cargado correctamente puede requerir revisar documentación de forma manual.

Esto puede provocar:

- Dificultad para conocer rápidamente el estado de una expedición.
- Comprobaciones repetitivas.
- Errores al identificar pedidos o materiales.
- Falta de trazabilidad ante incidencias.
- Dependencia de comunicación verbal o documentación física.
- Dificultad para saber qué pedidos están pendientes antes de cerrar una ruta.

El objetivo del proyecto es ofrecer una forma sencilla de saber:

**qué debe cargarse, qué se ha cargado, qué queda pendiente y qué ha tenido una incidencia.**

---

# 🚀 Solución

La aplicación organiza las expediciones por **ruta y fecha**.

Cada pedido dispone de un código QR que permite identificarlo rápidamente durante el proceso de carga.

El operario puede escanear el código y actualizar su estado directamente desde un teléfono móvil o dispositivo con cámara.

El sistema mantiene la información sincronizada mediante Firebase.

---

## 🔄 Flujo de funcionamiento

### 1️⃣ Importación de documentación

La aplicación procesa la información necesaria para generar la estructura de cada expedición.

Los pedidos quedan organizados por:

- Ruta
- Fecha
- Referencia
- Cliente
- Número de piezas
- Peso
- Identificador interno

---

### 2️⃣ Generación / asociación de códigos QR

Cada pedido dispone de un código QR que permite recuperar su información durante el proceso de carga.

El QR actúa como identificador del pedido y evita depender de búsquedas manuales.

---

### 3️⃣ Escaneo durante la carga

El operario utiliza la cámara del dispositivo para escanear el QR.

La aplicación identifica automáticamente el pedido correspondiente.

El usuario puede marcarlo como:

- ✅ Cargado
- ⚠️ Incidencia
- ⏳ Pendiente

---

### 4️⃣ Seguimiento de la ruta

Desde el panel de control puede visualizarse el estado general de la expedición.

Esto permite comprobar rápidamente:

- pedidos cargados;
- pedidos pendientes;
- incidencias;
- progreso general de la ruta.

---

### 5️⃣ Registro de incidencias

Si existe algún problema con un pedido, el operario puede registrarlo durante el propio proceso de carga.

Esto proporciona trazabilidad sobre qué ocurrió y evita depender exclusivamente de comunicaciones posteriores.

---

# 📱 Diseño orientado a uso en planta

Uno de los objetivos principales del proyecto fue que el sistema pudiera utilizarse directamente desde dispositivos móviles.

Por este motivo se priorizó:

- interfaz sencilla;
- acciones rápidas;
- pocos pasos por operación;
- lectura mediante cámara;
- visualización clara de estados;
- funcionamiento adaptado a un entorno operativo.

---

# 🧩 Arquitectura general

```text
DOCUMENTACIÓN / DATOS DE EXPEDICIÓN
              │
              ▼
      Procesamiento de pedidos
              │
              ▼
       Organización por rutas
              │
              ▼
       Generación / uso de QR
              │
        ┌─────┴─────┐
        ▼           ▼
   Operario      Panel de control
    móvil
        │
        ▼
Escaneo / actualización
        │
        ▼
      Firebase
        │
        ▼
Sincronización de estados
🛠️ Tecnologías utilizadas
Frontend
React
JavaScript
HTML
CSS
Backend / Datos
Firebase
Firestore
Firebase Authentication
Lectura QR
html5-qrcode
Herramientas
Visual Studio Code
Git / GitHub
Desarrollo asistido mediante IA
🧠 Competencias trabajadas

Más allá del desarrollo técnico, el proyecto implicó analizar un proceso operativo real y transformarlo en un flujo digital.

Entre las principales competencias trabajadas:

análisis de procesos;
digitalización de operaciones;
resolución de problemas;
diseño de flujos de trabajo;
modelado de datos;
bases de datos en tiempo real;
gestión de estados;
lectura de códigos QR;
desarrollo web;
diseño de interfaces orientadas al usuario;
automatización de procesos.
📊 Información manejada

Cada registro puede contener información como:

ID de pedido
Cliente
Referencia
Número de piezas
Peso
Ruta
Fecha
Estado de carga
Incidencia

Los datos mostrados públicamente en este repositorio y en las futuras demostraciones serán datos ficticios o anonimizados.

📸 Capturas del proyecto
Panel de rutas

Próximamente

<!-- ![Panel rutas](docs/panel-rutas.png) -->
Detalle de expedición

Próximamente

<!-- ![Detalle expedición](docs/detalle-ruta.png) -->
Escáner QR

Próximamente

<!-- ![Escáner QR](docs/escaner-qr.png) -->
Gestión de incidencias

Próximamente

<!-- ![Incidencias](docs/incidencias.png) -->
🎥 Demostración

Se añadirá una demostración breve del flujo completo:

Selección de ruta
      ↓
Visualización de pedidos
      ↓
Escaneo QR
      ↓
Pedido identificado
      ↓
Confirmación de carga / incidencia
      ↓
Actualización del estado
      ↓
Seguimiento de la expedición

🎬 Vídeo demostrativo: próximamente

💡 Enfoque del proyecto

Este proyecto no nació como un ejercicio académico.

Surge de observar un proceso operativo real e intentar responder a una pregunta:

¿Cómo podría digitalizar este flujo para hacerlo más sencillo, trazable y menos dependiente de comprobaciones manuales?

El desarrollo se realizó como proyecto personal, aplicando conocimientos de software, bases de datos y automatización a una necesidad de un entorno industrial.

🔐 Privacidad y código fuente

Por motivos de seguridad, privacidad y protección de la lógica de negocio:

el código fuente no se distribuye públicamente;
no se publican credenciales ni configuraciones de producción;
no se muestran datos reales de clientes;
las demostraciones utilizan información ficticia o anonimizada.

La arquitectura, funcionamiento y decisiones de diseño del proyecto sí se documentan públicamente con fines de portfolio profesional.
