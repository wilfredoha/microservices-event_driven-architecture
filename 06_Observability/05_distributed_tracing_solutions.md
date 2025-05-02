# 🛠️ 05 - Distributed Tracing Solutions

## 📦 Frameworks de Instrumentación para Distributed Tracing

Para recolectar trazas, es necesario **instrumentar el código** de nuestras aplicaciones. Esto se hace mediante frameworks y SDKs que capturan automáticamente o manualmente la información de trazabilidad.

### 🔧 OpenTelemetry

**OpenTelemetry** es una colección de APIs, SDKs y herramientas para **instrumentar, recolectar y exportar métricas, logs y trazas**. Es **open-source**, respaldado por la CNCF, y se ha convertido en el estándar de facto para observabilidad en sistemas distribuidos.

- **Lenguajes soportados:** C++, .NET, Erlang/Elixir, Go, Java, JavaScript, PHP, Python, Ruby, Rust, Swift.
- **Características:**
  - Captura trazas, métricas y logs con una misma interfaz.
  - Instrumentación automática disponible para muchos frameworks web y librerías comunes.
  - Compatible con múltiples backends de observabilidad (Jaeger, Zipkin, etc.).
- **Especificación:** OpenTelemetry también define una **especificación técnica** que unifica el comportamiento esperado en todas las implementaciones multi-lenguaje.

---

## 🗂️ Backends para Distributed Tracing

Una vez instrumentadas las aplicaciones, se necesita un sistema backend para **almacenar, visualizar y analizar** los datos de trazabilidad recolectados.

### 📌 Jaeger

- **Descripción:** Plataforma de trazabilidad distribuida, **open-source y cloud-native**, creada originalmente por Uber.
- **Ventajas:**
  - Escalable y sin costo.
  - Visualización de trazas, análisis de dependencia entre servicios y detección de cuellos de botella.
  - Se integra naturalmente con **OpenTelemetry**.
- **Casos de uso:** Diagnóstico de latencia, análisis de flujos de trabajo distribuidos, análisis de rendimiento.

### 📌 Zipkin

- **Descripción:** Sistema de trazabilidad distribuido desarrollado originalmente por Twitter, inspirado en el paper de Google sobre Dapper.
- **Almacenamiento:** Soporte para almacenamiento en memoria, Cassandra, Elasticsearch, MySQL y más.
- **Instrumentación:** Compatible con múltiples SDKs oficiales y de la comunidad.
- **Ventajas:**
  - Ligero y fácil de desplegar.
  - Buena integración con ecosistemas Spring y otros entornos Java.

### ☁️ Uptrace

- **Descripción:** Plataforma comercial basada en OpenTelemetry.
- **Características:**
  - Recolección y visualización de métricas, trazas y logs.
  - Integración para performance monitoring y análisis completo de sistemas distribuidos.
  - Interfaz moderna, alertas, dashboards personalizados.
- **Ventajas:**
  - Reducción de esfuerzo operativo al ser una solución gestionada.
  - Ideal para equipos que buscan observabilidad sin gestionar infraestructura.

---

## ✅ Conclusión

La trazabilidad distribuida es esencial para entender el comportamiento de sistemas modernos basados en microservicios. OpenTelemetry ha emergido como el estándar unificado para instrumentación, y puede ser integrado con múltiples backends como **Jaeger**, **Zipkin** y **Uptrace**, permitiendo flexibilidad tanto para soluciones self-managed como comerciales.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)