# 🔧 Contract Tests Solutions

Las pruebas de contrato son fundamentales para mantener la compatibilidad y la confianza entre servicios en una arquitectura de microservicios. A continuación se describen las soluciones más populares para implementar este tipo de pruebas.

---

## 🧪 Pact

**Pact** es una herramienta de código abierto para pruebas de contrato centradas en el consumidor. Permite que tanto consumidores como proveedores definan y verifiquen contratos de API de forma automática.

### Características:
- Admite múltiples lenguajes y frameworks (Java, JavaScript, .NET, Ruby, Go, Python, etc.).
- Fomenta el desarrollo orientado por contratos (Consumer Driven Contract - CDC).
- Proporciona herramientas para generar, verificar y publicar contratos.
- Ofrece soporte para comunicación síncrona (REST, gRPC).

### Ventajas:
- Amplio soporte de comunidad.
- Buen ecosistema de herramientas (Pact Broker, CLI).
- Fácil de integrar en CI/CD.

---

## 🌱 Spring Cloud Contract

**Spring Cloud Contract** es un proyecto de código abierto que permite implementar pruebas de contrato en aplicaciones basadas en la JVM, como servicios en Spring Boot.

### Características:
- Compatible con **Consumer Driven Contract**.
- Permite definir contratos en **Groovy DSL**, **YAML** o **JSON**.
- Integra validación de contratos como parte del proceso de compilación.
- Genera automáticamente stubs para consumidores.

### Ventajas:
- Integración profunda con el ecosistema Spring.
- Automatización completa de verificación y generación de mocks.
- Ideal para entornos corporativos con Java y Spring.

---

## ☁️ PactFlow

**PactFlow** es una solución comercial que gestiona el ciclo de vida de los contratos definidos con herramientas como Pact o Spring Cloud Contract. Proporciona flujos de trabajo para facilitar su integración en pipelines de CI/CD.

### Características:
- Soporte completo para múltiples lenguajes (JVM, JavaScript, .NET, Golang, Ruby, Python, PHP, C++, Rust, Objective-C/Swift).
- Consola web para la gestión de contratos y sus versiones.
- Integración con herramientas CI como GitHub Actions, GitLab CI, Jenkins, etc.
- Seguridad, control de acceso y auditoría de cambios en contratos.

### Ventajas:
- Reduce la complejidad de gestionar contratos en equipos grandes.
- Asegura sincronización entre consumidores y proveedores.
- Ideal para organizaciones con múltiples equipos y entornos.

---

## ✅ Conclusión

Las pruebas de contrato ayudan a reducir el riesgo de errores en tiempo de ejecución al validar los contratos de comunicación entre servicios. La elección de una solución dependerá del lenguaje de programación, el ecosistema tecnológico y el nivel de automatización requerido en los pipelines de CI/CD.

| Herramienta         | Tipo        | Lenguajes soportados                    | Casos ideales                         |
|---------------------|-------------|----------------------------------------|----------------------------------------|
| Pact                | Open Source | Java, JS, .NET, Go, Python, etc.       | CDC, múltiples lenguajes               |
| Spring Cloud Contract | Open Source | JVM (Groovy, Java, Kotlin)             | Entornos Spring Boot                   |
| PactFlow            | Comercial   | Todos los principales lenguajes        | Gestión avanzada de contratos en CI/CD |

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/05_Testing_Microservices/02_contract_tests_production_testing.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/06_Observability/01_intro_observability.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)