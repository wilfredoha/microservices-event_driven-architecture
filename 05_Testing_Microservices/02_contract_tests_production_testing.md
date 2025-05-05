# 🧪 Contract Tests & Production Testing in Microservices Architecture

## 🧩 Complejidad de las Pruebas de Integración y End-to-End en Microservicios

La arquitectura de microservicios introduce múltiples puntos de interacción entre servicios, lo que hace que las pruebas de integración y end-to-end (E2E) sean costosas y difíciles de mantener. Los principales desafíos incluyen:

- **Ambientes complejos de prueba**: replicar todos los servicios y sus dependencias es difícil.
- **Tiempos prolongados de ejecución**: las pruebas E2E suelen ser lentas.
- **Pruebas frágiles**: fallas menores pueden propagar errores falsos positivos.
- **Acoplamiento excesivo**: los cambios en un servicio pueden romper pruebas de otros.

## 🤖 Pruebas de Integración con Mocks

Una estrategia común para simplificar las pruebas es usar **mocks** que simulen servicios externos durante las pruebas de integración.

**Ventajas:**
- Reducción de dependencias reales.
- Ejecución más rápida y aislada.
- Mayor control de escenarios.

**Limitaciones:**
- No garantizan el cumplimiento del contrato real.
- Riesgo de divergencia entre el mock y el servicio real.

## 📄 Contract Tests en Comunicación Sincrónica

Los **Contract Tests** verifican que tanto el consumidor como el proveedor de una API respeten un contrato común, ayudando a mantener la compatibilidad entre microservicios.

**Características:**
- Son más ligeros que pruebas E2E.
- Se enfocan en la **estructura, formato y comportamiento esperado de la API**.
- Automatizables y ejecutables en el pipeline de CI.

## 📬 Contract Tests en Comunicación Asíncrona

En arquitecturas basadas en eventos, los **contract tests** también son necesarios para verificar:

- Que los productores envían eventos con el formato correcto.
- Que los consumidores puedan manejar los eventos esperados.
- Que los esquemas de eventos sean consistentes (por ejemplo, usando **Avro** o **JSON Schema**).

Estos contratos pueden validarse con herramientas como **Pact**, **Testcontainers**, o validadores de esquemas.

## 🚀 Pruebas en Producción

Para minimizar el riesgo al desplegar microservicios, se emplean estrategias de pruebas en producción:

### 🟩 Blue/Green Deployment

- Dos entornos idénticos (Blue y Green).
- Se redirige el tráfico al nuevo entorno (Green) después de probarlo.
- Permite rollback inmediato si hay errores.

### 🐦 Canary Testing

- Se despliega una nueva versión a un pequeño porcentaje de usuarios.
- Se monitorean métricas clave (errores, latencia).
- Si es exitosa, se aumenta el tráfico gradualmente.

**Beneficios:**
- Reducción del riesgo de fallas masivas.
- Permite pruebas en condiciones reales.
- Mejora la confianza en despliegues frecuentes.

---

✅ **Conclusión**:  
Los contract tests permiten asegurar compatibilidad entre microservicios sin necesidad de costosas pruebas E2E. Complementarlos con despliegues progresivos como Blue/Green y Canary asegura calidad y confiabilidad en producción.

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/05_Testing_Microservices/01_testing_pyramid.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/05_Testing_Microservices/03_contract_tests_solutions.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)