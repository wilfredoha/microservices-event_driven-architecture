# 🔀 CQRS Pattern (Command Query Responsibility Segregation)

## 📌 Introducción al Patrón CQRS

**CQRS** (Command Query Responsibility Segregation) es un patrón arquitectónico que separa explícitamente las operaciones de lectura (**Queries**) de las operaciones de escritura (**Commands**) en un sistema.

Esta separación permite optimizar y escalar de forma independiente los flujos de lectura y escritura, especialmente útil en arquitecturas de microservicios y sistemas distribuidos con alta carga o requerimientos diferenciados.

![CQRS Pattern](images/cqrs.png)

### 🔧 Componentes clave

- **Command**: Modifica el estado del sistema (crear, actualizar, eliminar). No retorna datos, solo confirma éxito o falla.
- **Query**: Recupera datos. No modifica el estado del sistema. Solo retorna información.

### 🔁 Sincronización mediante eventos

En implementaciones distribuidas, donde Command y Query acceden a diferentes bases de datos (eventualmente desacopladas), se puede usar un **Message Broker** para emitir eventos después de ejecutar comandos.  
Estos eventos son consumidos por los componentes de lectura para actualizar sus propias bases de datos, manteniéndose sincronizados de forma **eventual**.

---

## 🛠️ Casos de Uso de CQRS en Arquitectura de Microservicios

### ✅ Separación de responsabilidades (SRP)

Separar comandos y consultas permite aplicar de forma más estricta el principio de **responsabilidad única**:
- La lógica de negocio relacionada con cambios de estado se mantiene independiente de las optimizaciones para consultas.
- Cada flujo se puede escalar, desplegar o evolucionar de forma aislada.

### ⚡ Mejor rendimiento y escalabilidad

- Las consultas pueden implementarse sobre una base de datos optimizada para lectura (por ejemplo, con modelos de agregación, caché o proyecciones específicas).
- Se puede aplicar almacenamiento especializado para comandos (por ejemplo, una base de datos relacional con control transaccional fuerte).

### 🔗 Unificación de datos de diferentes servicios

Cuando una vista necesita combinar datos de múltiples microservicios:
- Cada servicio mantiene su fuente de datos aislada (Command Side).
- Una vista compuesta puede mantenerse sincronizada de forma **eventual** (Read Side), escuchando eventos y actualizando su propia copia.
- Esto permite consultas complejas sin violar el principio de independencia de los microservicios.

---

## 🎯 Conclusión

El patrón CQRS es ideal para arquitecturas distribuidas con:
- Altos volúmenes de lectura.
- Reglas de negocio complejas para comandos.
- Necesidad de vistas unificadas sin acoplar servicios.

La combinación con **event-driven architecture** y **bases de datos desacopladas** potencia aún más su efectividad, aunque también introduce complejidad adicional (sincronización eventual, consistencia, idempotencia).

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/04_Event_Driven_Patterns/01_saga_pattern.md)   [Siguiente](hhttps://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/04_Event_Driven_Patterns/03_event_sourcing.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)