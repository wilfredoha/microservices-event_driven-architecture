# 📦 Microservices Boundaries - Core Principles

## ¿Por qué son importantes los límites en los microservicios?

Definir límites adecuados entre microservicios es esencial para lograr una arquitectura que sea escalable, mantenible y resiliente.  
Un buen límite asegura que cada microservicio pueda evolucionar de manera independiente, minimizando dependencias innecesarias y optimizando la colaboración entre equipos.

A continuación, exploramos los tres principios fundamentales para definir estos límites de forma efectiva.

---

## 🔹 Alta Cohesión

La cohesión mide **qué tan relacionadas y enfocadas** están las responsabilidades internas de un microservicio.

- Un servicio con alta cohesión agrupa funcionalidades que **naturalmente pertenecen juntas** dentro del dominio del negocio.
- Los cambios internos tienden a estar relacionados y afectan principalmente al propio servicio, no a otros.
- Mejora la claridad, facilita el mantenimiento y acelera el desarrollo.

**Ejemplo:**  
Un servicio de `Gestión de Pedidos` debe encargarse únicamente de procesos como creación, actualización y seguimiento de pedidos. No debe gestionar usuarios ni pagos.

**Importante:**  
Alta cohesión no significa agrupar funcionalidades arbitrarias para reducir el número de servicios. Cada funcionalidad debe estar lógicamente conectada.

---

## 🔹 Principio de Responsabilidad Única (SRP)

Basado en el **Single Responsibility Principle** de la ingeniería de software:

> "Un microservicio debe tener una sola razón para cambiar."

- Cada servicio debe ser responsable de **una única área del negocio o función principal**.
- Ayuda a evitar servicios "monstruo" que manejan múltiples aspectos no relacionados, lo que complica la evolución independiente.
- Hace que los servicios sean más simples de entender, probar y desplegar.

**Ejemplo:**  
Un servicio que maneje exclusivamente `Autenticación` y otro que gestione `Perfil de Usuario`, en lugar de un solo servicio "Usuarios" que haga ambas cosas.

**Clave práctica:**  
Si un servicio requiere cambios por razones diferentes (por ejemplo, cambios de negocio y cambios técnicos), probablemente debería dividirse.

---

## 🔹 Bajo Acoplamiento

El acoplamiento se refiere a **qué tan dependientes son los microservicios entre sí**.

- Bajo acoplamiento significa que los servicios interactúan **de forma mínima y controlada**, principalmente a través de interfaces estables como APIs o eventos.
- Cada microservicio puede evolucionar, escalar y desplegarse sin verse afectado por cambios en otros servicios.
- Se promueve el uso de **comunicación asíncrona** (por ejemplo, eventos) para reducir las dependencias temporales.

**Ejemplo:**  
En lugar de que el servicio de `Pagos` llame directamente al servicio de `Inventario`, ambos publican y consumen eventos relevantes (`PedidoPagado`, `InventarioActualizado`).

**Consecuencia de alto acoplamiento:**  
Cambiar un servicio obliga a cambiar otros, introduciendo errores y ralentizando la entrega.

---

## ✅ Resumen visual

| Principio | ¿Qué busca lograr? | Consecuencias si no se cumple |
|:---|:---|:---|
| Cohesión | Funcionalidades relacionadas dentro del mismo servicio | Código confuso y difícil de mantener |
| Responsabilidad Única (SRP) | Cada servicio enfocado en un área específica | Servicios inflados, difíciles de evolucionar |
| Bajo Acoplamiento | Servicios independientes con interfaces bien definidas | Cambios constantes y errores en cascada |

---

> ✨ Aplicando estos principios de forma consciente, los microservicios se convierten en componentes autónomos, robustos y preparados para crecer junto con el negocio.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)