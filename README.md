# JOMPARE - Comparador de Especificaciones de Teléfonos Móviles

## 📝 1. Definición del Problema
En el mercado tecnológico actual, la oferta de teléfonos inteligentes es masiva. Los usuarios enfrentan serias dificultades al intentar elegir un dispositivo que se adapte a sus necesidades debido a:
* **Dispersión de la información:** Los datos técnicos se encuentran fragmentados en múltiples páginas web con formatos inconsistentes.
* **Complejidad técnica:** Las especificaciones de hardware a menudo se presentan de forma confusa para el consumidor promedio.
* **Falta de herramientas offline:** La mayoría de los comparadores actuales requieren conexión activa a internet, limitando su uso en zonas con conectividad reducida o dentro de tiendas físicas.

### Solución Propuesta
**JOMPARE** resuelve esta problemática ofreciendo una base de datos local robusta, una interfaz de usuario optimizada bajo los principios de *Material Design 3* y un sistema de comparación directa estructurado en una matriz limpia que facilita la toma de decisiones informadas de manera instantánea y 100% offline.

---

## 👥 2. Historias de Usuario (User Stories)

| ID | Como... | Quiero... | Para... | Criterios de Aceptación |
| :--- | :--- | :--- | :--- | :--- |
| **US-01** | Usuario general | Buscar un teléfono por su marca o modelo en una barra de búsqueda. | Encontrar rápidamente el dispositivo del que deseo conocer sus características. | * El sistema debe filtrar en tiempo real mientras se escribe.<br>* Si el teléfono no existe, debe mostrar un estado vacío amigable. |
| **US-02** | Usuario comprador | Seleccionar hasta 3 teléfonos simultáneamente y presionar "Comparar". | Ver una tabla comparativa que contraste sus componentes lado a lado. | * La pantalla de comparación debe alinear los componentes (RAM, CPU, Batería).<br>* Debe permitir el desplazamiento horizontal si las especificaciones son extensas. |
| **US-03** | Entusiasta tecnológico | Aplicar filtros avanzados (ej. solo pantallas OLED o más de 8GB de RAM). | Reducir el catálogo global solo a los dispositivos que cumplen mi estándar. | * Los filtros se pueden acumular.<br>* Debe incluir un botón para limpiar todos los filtros aplicados con un solo toque. |
| **US-04** | Usuario en movimiento | Utilizar todas las funciones de comparación dentro de un centro comercial sin señal. | Consultar los datos técnicos de inmediato sin consumir datos móviles ni depender de Wi-Fi. | * Toda la información del catálogo inicial debe cargarse desde el almacenamiento local sin requerir llamadas de red. |

---

## 🏗️ 3. Arquitectura del Software
La aplicación está construida siguiendo las guías oficiales de Google, implementando el **Patrón de Arquitectura MVVM (Model-View-ViewModel)**. El proyecto está dividido limpiamente en tres capas fundamentales para garantizar el desacoplamiento y la facilidad de mantenimiento:

* **Capa de UI (Views):** Actividades, fragmentos y diseños XML encargados exclusivamente de mostrar los datos al usuario mediante componentes de *Material Design 3*.
* **Capa de Lógica (ViewModel):** Retiene y prepara el estado de la interfaz de manera segura ante cambios de configuración (como la rotación de la pantalla al leer una tabla comparativa horizontal).
* **Capa de Datos (Repository):** Gestiona el acceso al catálogo técnico de dispositivos de forma asíncrona.

---

## 🛠️ 4. Tecnologías Elegidas y Frameworks
* **Lenguaje de Programación:** [Kotlin](https://kotlinlang.org/) (100% nativo), garantizando un código moderno, seguro y eficiente.
* **Persistencia de Datos Local:** [Room Database](https://developer.android.com/training/data-storage/room). Se eligió Room sobre soluciones Cloud (como Firebase) para garantizar el funcionamiento **100% offline** y optimizar las consultas relacionales del catálogo técnico mediante DAOs validados en tiempo de compilación.
* **Concurrencia:** [Kotlin Coroutines](https://kotlinlang.org/docs/coroutines-overview.html) para realizar operaciones asíncronas en hilos secundarios (I/O) al consultar la base de datos de los teléfonos sin congelar la pantalla.
* **Diseño de Interfaz:** [Material Design 3](https://m3.material.io/) junto con componentes XML nativos avanzados para lograr una estética moderna y limpia.
* **Control de Versiones:** Git & [GitHub](https://github.com/) para el alojamiento y gestión del código fuente.

---
*Desarrollado con fines académicos y de ingeniería de software - 2026.*
