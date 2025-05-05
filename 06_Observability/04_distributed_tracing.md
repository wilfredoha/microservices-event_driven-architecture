# 🔍 04 - Distributed Tracing en Microservicios

## 🎯 Motivación: ¿Por qué usar Distributed Tracing?

En arquitecturas de microservicios, una única solicitud del usuario puede atravesar múltiples servicios, cada uno manejando una parte del proceso. Si ocurre una falla o se presenta una latencia elevada, **identificar la causa exacta puede ser extremadamente difícil**.

**Distributed Tracing** (trazado distribuido) permite seguir el camino completo de una solicitud a través de múltiples servicios. Ayuda a responder preguntas como:
- ¿Dónde se originó la lentitud?
- ¿Qué servicio falló exactamente?
- ¿Cómo fluyen las solicitudes entre componentes?

### Beneficios clave:
- Permite **aislar componentes con fallos**.
- Ayuda a detectar **problemas de comunicación entre servicios**.
- Facilita el análisis de **cuellos de botella**.

---

## 🧩 Terminología y Funcionamiento

Distributed tracing se basa en **propagar información de trazabilidad** (trace context) junto con cada solicitud.

### Términos clave:

| Término           | Descripción                                                                 |
|------------------|------------------------------------------------------------------------------|
| **Trace ID**      | Identificador único para una solicitud completa que viaja a través de servicios. |
| **Span**          | Representa una operación individual dentro de un servicio. Tiene timestamps y puede anidarse (jerarquía). |
| **Trace Context** | Información que permite conectar múltiples spans como parte de una misma trace. |
| **Tracing Library/SDK** | Biblioteca usada para instrumentar el código y capturar trazas. Ej: OpenTelemetry. |
| **Trace Data**    | Información recolectada de spans: duración, errores, relaciones entre llamadas, etc. |

### ¿Cómo funciona?
1. Se genera un **Trace ID** cuando una solicitud entra al sistema.
2. Cada servicio añade un **span** al trace.
3. Se propaga el **trace context** entre servicios a través de headers HTTP o mensajes.
4. La traza se visualiza en herramientas como **Jaeger**, **Zipkin** o **X-Ray**.

---

## ⚠️ Retos en Arquitecturas Basadas en Eventos

Las arquitecturas **event-driven** (basadas en eventos) presentan desafíos únicos para implementar distributed tracing:

### 1. Instrumentación Manual
- Requiere agregar bibliotecas específicas al código.
- El desarrollador debe **entender y aplicar manualmente el trazado**.
- Puede haber spans demasiado amplios o faltantes.
- Propagar el trace context por eventos no es automático.

### 2. Costo
- Agentes de monitoreo e infraestructura adicional.
- Costos de almacenamiento para traces.
- Costos de mantenimiento de herramientas de tracing.

### 3. Demasiada Información
- Las trazas pueden volverse muy grandes en sistemas complejos.
- Dificultad para navegar o extraer valor sin filtros adecuados.

---

## ✅ Conclusión

**Distributed Tracing** es una herramienta esencial para diagnosticar problemas en sistemas distribuidos, pero su implementación tiene retos técnicos y de costo, especialmente en arquitecturas basadas en eventos. Adoptar buenas prácticas de instrumentación y limitar el volumen de trazas recolectadas es clave para obtener valor sin sobrecargar el sistema.


---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/06_Observability/03_metrics.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/06_Observability/05_distributed_tracing_solutions.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)