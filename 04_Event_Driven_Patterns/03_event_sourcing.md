# 📜 Event Sourcing Pattern

## 📌 Introducción

**Event Sourcing** es un patrón arquitectónico en el cual el estado de una entidad o sistema no se almacena como un conjunto de valores actuales (como en los modelos tradicionales), sino como una **secuencia inmutable de eventos** que representan todos los cambios que han ocurrido en el tiempo.

Cada evento representa una acción realizada (por ejemplo: `CuentaCreada`, `SaldoDepositado`, `SaldoRetirado`) y puede ser reproducido para reconstruir el estado actual de una entidad.

---

## ⚙️ ¿Cómo funciona Event Sourcing?

1. Cada vez que ocurre una acción que modifica el estado, se genera un **evento** y se guarda en un **Event Store**.
2. No se guarda el nuevo estado directamente, sino el evento que produjo ese cambio.
3. Para obtener el estado actual de una entidad, se **reproducen** (replay) todos los eventos desde el inicio.

---

## ✅ Beneficios del Event Sourcing

- **Auditabilidad total**: puedes rastrear exactamente qué ocurrió y cuándo.
- **Debugging e investigación**: posible reconstruir el estado en cualquier punto del tiempo.
- **Reacciones asíncronas**: otros microservicios pueden reaccionar a eventos de dominio en tiempo real.
- **Flexibilidad para proyecciones**: diferentes vistas de datos pueden derivarse de la misma secuencia de eventos.
- **Reprocesamiento**: puedes regenerar vistas (read models) sin tocar la fuente de verdad.

---

## ⚠️ Desafíos y consideraciones

- **Complejidad adicional**: escribir y leer datos es más complejo que en CRUD tradicional.
- **Necesidad de proyecciones (Read Models)**: para consultas eficientes, se deben mantener vistas materializadas derivadas de los eventos.
- **Evolución del esquema de eventos**: los eventos deben versionarse con cuidado para manejar cambios de negocio.
- **Gestión del almacenamiento de eventos**: puede crecer considerablemente con el tiempo.

---

## 🛠️ Casos de uso comunes

- Sistemas con alta necesidad de trazabilidad o cumplimiento (banca, salud, legal).
- Aplicaciones donde los datos deben reconstruirse en diferentes contextos.
- Sistemas que utilizan **CQRS**: Event Sourcing es una combinación natural con este patrón, ya que los eventos generados por los comandos pueden alimentar las vistas de lectura.

---

## 🧠 Diferencia con CRUD tradicional

| Característica         | CRUD tradicional                 | Event Sourcing                            |
|------------------------|----------------------------------|--------------------------------------------|
| Persistencia           | Último estado                    | Todos los eventos que llevaron a ese estado |
| Auditable              | Parcial (requiere logs externos) | Totalmente auditable                        |
| Escenario de recuperación | Difícil                         | Preciso y reproducible                     |
| Estructura de datos    | Tablas relacionales              | Streams de eventos                         |

---

## 🎯 Conclusión

Event Sourcing es una poderosa estrategia para microservicios donde el **registro histórico**, la **flexibilidad de proyecciones** y la **capacidad de recuperación** son prioritarias.  
Sin embargo, implica una curva de aprendizaje y una arquitectura más compleja que debe ser justificada por los requerimientos del sistema.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)