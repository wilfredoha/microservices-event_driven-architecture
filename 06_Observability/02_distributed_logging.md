# 📝 Distributed Logging en Arquitectura de Microservicios

## 🔍 ¿Qué es Logging?

El *logging* es el proceso de registrar información sobre eventos, acciones, errores y excepciones que ocurren dentro de un sistema. Estos registros pueden ser utilizados para:

- Diagnóstico y solución de errores.
- Auditoría y cumplimiento.
- Análisis de comportamiento de usuarios y aplicaciones.
- Seguimiento del estado del sistema en producción.

En sistemas monolíticos, estos logs suelen estar en un solo archivo o ubicación. Sin embargo, en arquitecturas de microservicios, donde múltiples servicios se ejecutan de forma distribuida, se necesita una estrategia de **logging distribuido**.

---

## 🌐 ¿Qué es Distributed Logging?

En una arquitectura distribuida, cada microservicio genera sus propios logs. El *distributed logging* es la práctica de recolectar, almacenar, correlacionar y analizar todos esos logs de manera centralizada para poder obtener visibilidad completa del sistema.

---

## ✅ Mejores Prácticas para Distributed Logging

### 1. 📦 Sistema Centralizado de Logs

Utiliza una solución de logging centralizada como ELK Stack (Elasticsearch, Logstash, Kibana), Fluentd + Grafana, o servicios como Amazon CloudWatch o Datadog para recolectar y visualizar logs provenientes de múltiples servicios.

### 2. 🧱 Estructura Predefinida (Schema)

Los logs deben tener una estructura uniforme (por ejemplo, JSON), para que puedan ser fácilmente procesados por humanos y herramientas automáticas. Esto incluye campos como:

- `timestamp`
- `level`
- `message`
- `service_name`
- `host`
- `correlation_id`

### 3. 🚦 Niveles de Log (Log Level)

Define claramente los niveles de severidad de los logs:

- `DEBUG`: información detallada para desarrolladores.
- `INFO`: eventos relevantes del flujo normal.
- `WARN`: situaciones inusuales pero no críticas.
- `ERROR`: errores que requieren atención.
- `FATAL`: errores graves que detienen el sistema.

### 4. 🔗 Correlation ID

Incluye un `correlation_id` en todos los logs que pertenecen a una misma solicitud (request). Este identificador único permite rastrear una transacción a través de múltiples servicios.

### 5. 🧠 Agregar Información Contextual

Para facilitar el análisis, incluye metadatos relevantes en cada entrada de log:

- Nombre del servicio (`service_name`)
- Nombre del host o contenedor (`host`)
- ID del usuario (`user_id`)
- Marca de tiempo (`timestamp`)
- Path o endpoint involucrado
- Resultado del proceso

### 6. 🔐 Buenas Prácticas de Seguridad y Rendimiento

- No loguees datos sensibles como contraseñas, tokens, o información personal identificable (PII).
- Registra solo la información necesaria: evitar logs excesivos que aumenten el almacenamiento y dificulten el análisis.

---

## 🧩 Conclusión

El logging distribuido es esencial para tener visibilidad y trazabilidad en sistemas compuestos por múltiples microservicios. Al seguir buenas prácticas como estandarización, centralización, uso de correlation IDs y contexto enriquecido, se facilita el monitoreo, el análisis de fallos y la mejora continua del sistema.

En el siguiente módulo exploraremos el uso de métricas como pilar adicional de observabilidad.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)