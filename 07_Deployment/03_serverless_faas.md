# ⚙️ 03 - Serverless & Function-as-a-Service (FaaS)

## 🚀 Motivación para el Despliegue Serverless con FaaS

Tradicionalmente, los equipos deben aprovisionar, configurar y mantener servidores para ejecutar sus aplicaciones. Este enfoque conlleva altos **costos de infraestructura** (capacidad reservada y subutilizada) y **costos de desarrollo**, ya que se invierte tiempo en tareas operativas en lugar de enfocarse en la lógica del negocio.

**Serverless** y en particular **FaaS (Function as a Service)**, busca resolver este problema permitiendo ejecutar funciones bajo demanda, eliminando la necesidad de administrar servidores.

---

## 🧠 ¿Qué es FaaS?

Function-as-a-Service (FaaS) es un modelo de ejecución dentro de las arquitecturas serverless donde el desarrollador escribe funciones que se ejecutan en respuesta a eventos o peticiones, sin preocuparse por la infraestructura subyacente.

- Tú defines:
  - El tipo de evento que debe activar la función (HTTP, colas, cron jobs, cambios en el almacenamiento, etc.)
  - La lógica de negocio que debe ejecutarse
- El proveedor cloud administra:
  - El aprovisionamiento de infraestructura
  - La escalabilidad automática
  - La facturación por uso real

### 💰 Modelo de Precios

Pagas únicamente por el número de invocaciones y el tiempo de ejecución (en milisegundos), así como por la memoria asignada.

---

## ✅ Beneficios de FaaS

| Beneficio                             | Descripción                                                                 |
|--------------------------------------|-----------------------------------------------------------------------------|
| Reducción de costos de infraestructura | No necesitas mantener servidores encendidos cuando no hay tráfico          |
| Escalabilidad automática              | El sistema escala de manera automática ante un aumento repentino de tráfico |
| Menor costo de desarrollo             | Los equipos se enfocan más en la lógica de negocio que en el manejo de servidores |
| Menor complejidad de despliegue       | Ideal para empaquetar y desplegar microservicios o funciones aisladas      |

---

## ⚠️ Desventajas de FaaS

| Desventaja                           | Descripción                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------|
| Costos impredecibles                | Si cambia el patrón de tráfico, los costos pueden aumentar considerablemente |
| Performance variable                | Al ser multi-tenant, se comparte la infraestructura (noisy neighbor)        |
| Tiempo de arranque (cold starts)    | Las funciones pueden demorar más en su ejecución inicial                   |
| No apto para cargas de trabajo persistentes o de larga duración | Ideal para tareas cortas y asincrónicas                                     |

---

## 📊 Comparativa: Opciones de Despliegue

| Tipo de Despliegue     | Costo          | Seguridad                          | Rendimiento                         |
|------------------------|----------------|------------------------------------|-------------------------------------|
| Multi-Tenant VM        | Bajo           | Aislamiento lógico                 | Variable (noisy neighbor)           |
| Single-Tenant VM       | Medio - Alto   | Aislamiento físico parcial         | Más predecible                      |
| Dedicated Host         | Alto           | Aislamiento total                  | Máximo control y rendimiento        |
| **FaaS**               | Bajo a medio   | Aislamiento virtual multi-tenant   | Escalable, pero con cold starts     |

---

## 📝 Conclusión

FaaS es ideal para aplicaciones que requieren alta escalabilidad con poca gestión operativa y donde las funciones son pequeñas, aisladas y ejecutadas por eventos. Aunque trae ventajas importantes en costos y eficiencia operativa, no es adecuado para todos los tipos de carga de trabajo, especialmente aquellas que requieren consistencia de rendimiento o conexiones persistentes.

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/02_cloud_vm_solutions.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/04_serverless_faas_solutions.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)