# 🎯 Event-Driven Architecture - Use Cases and Patterns

La arquitectura basada en eventos permite construir sistemas altamente desacoplados, escalables y flexibles, ideales para una variedad de escenarios en los que la asincronía y la resiliencia son fundamentales.

---

## 📌 Casos de uso de Event-Driven Architecture

A continuación, se presentan algunos escenarios comunes donde EDA ofrece beneficios significativos:

### 🔥 Fire and Forget
El productor emite un evento y no espera una respuesta. Útil para acciones no críticas o cuando no es necesario conocer el resultado de inmediato (ej. registrar logs o métricas).

### 📬 Reliable Delivery
Cuando es fundamental garantizar que todos los eventos lleguen a sus consumidores, incluso ante fallos temporales. Es esencial para sistemas financieros, de inventario o flujos de trabajo críticos.

### 🌊 Infinite Streams of Events
Casos como sensores IoT, seguimiento en tiempo real, procesamiento de logs o clickstreams en sitios web. Los eventos fluyen continuamente y deben ser procesados en tiempo real o por lotes.

### 🔍 Anomaly Detection / Pattern Recognition
El análisis de grandes volúmenes de eventos permite identificar patrones anómalos como fraudes, fallos de seguridad o comportamientos inusuales. Se puede entrenar modelos de ML o aplicar reglas predefinidas.

### 📣 Broadcasting
Un solo evento es consumido por múltiples componentes interesados. Por ejemplo, un evento de "nuevo usuario registrado" puede ser consumido por el sistema de bienvenida, CRM y analítica.

### 🧺 Buffering
Al desacoplar productor y consumidor, el sistema puede manejar picos de carga. El message broker actúa como un buffer, almacenando eventos hasta que puedan ser procesados.

---

## 📌 Casos de uso del modelo Request-Response

Aunque EDA tiene muchas ventajas, el modelo tradicional **request-response** sigue siendo más adecuado en ciertas situaciones:

### ⚡ Respuesta inmediata requerida
Cuando el cliente necesita una respuesta inmediata con datos (por ejemplo, consultar el saldo de una cuenta), el enfoque sincrónico es más eficiente.

### 🔄 Interacciones simples
Operaciones CRUD básicas o acciones con lógica de negocio sencilla se benefician de la simplicidad del modelo sincrónico.

---

## 🧭 Patrones de entrega de eventos

La forma en que los eventos se distribuyen y consumen varía según el patrón de entrega adoptado:

### 🚀 Event Streaming
- Transmisión continua y ordenada de eventos.
- Ideal para procesamiento de datos en tiempo real.
- Soporta **entrega confiable** y permite detección de **anomalías o patrones**.
- Ejemplos: Apache Kafka, AWS Kinesis.

### 📢 Publish / Subscribe (Pub/Sub)
- Los productores emiten eventos sin conocimiento de los consumidores.
- Los consumidores se suscriben a temas específicos y reciben los eventos automáticamente.
- Soporta **fire and forget**, **broadcasting** y **buffering**.
- Ejemplos: Google Pub/Sub, AWS SNS, RabbitMQ.

---

## ✅ Conclusión

Event-Driven Architecture ofrece un enfoque poderoso para manejar flujos de datos complejos, responder en tiempo real y desacoplar componentes del sistema. La elección del patrón adecuado (event streaming o pub/sub) y del modelo (EDA vs request-response) dependerá del caso de uso, los requisitos de rendimiento y la naturaleza del sistema.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)