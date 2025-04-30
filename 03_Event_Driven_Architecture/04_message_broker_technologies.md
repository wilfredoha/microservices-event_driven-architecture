# 🧵 Message Broker Technologies - Delivery Guarantees

Los **message brokers** son componentes clave en arquitecturas basadas en eventos, actuando como intermediarios confiables entre productores y consumidores. Cada tecnología de broker implementa diferentes niveles de garantía de entrega, lo cual impacta directamente en la consistencia, latencia y confiabilidad del sistema.

---

## 🎯 Apache Kafka

Apache Kafka es una plataforma distribuida de transmisión de eventos diseñada para manejar grandes volúmenes de datos con baja latencia y alta durabilidad.

### 🔸 Producer Delivery Semantics
- **At-Most-Once**: El productor no espera confirmación del broker. Riesgo de pérdida si falla la transmisión.
- **At-Least-Once**: El productor reintenta hasta recibir confirmación. Riesgo de duplicación si el mensaje se reenvía.
- **Exactly-Once**: Kafka permite una entrega exacta cuando se habilita el procesamiento de transacciones y el almacenamiento entre topics.

### 🔸 Consumer Receipt Semantics
- **At-Most-Once**: El consumidor confirma la recepción antes de procesar. Si falla durante el procesamiento, el mensaje ya fue marcado como leído.
- **At-Least-Once**: El consumidor procesa y luego confirma. Si falla antes de confirmar, el mensaje se vuelve a entregar.
- **Exactly-Once**: Lograble con control de offset transaccional y procesamiento idempotente o atómico.

> **Nota:** Kafka soporta **Exactly Once Delivery Semantics** cuando se transfieren y procesan datos entre topics, no necesariamente hacia o desde sistemas externos.

---

## 🟢 Amazon SQS

Amazon Simple Queue Service (SQS) es una solución de colas completamente administrada que permite desacoplar y escalar sistemas distribuidos.

### 🔸 SQS Standard Queues
- Garantía de **At-Least-Once**: cada mensaje se entrega al menos una vez, con posibilidad de duplicación.

### 🔸 SQS FIFO Queues
- Ofrecen orden estricto y procesamiento **exactamente una vez** cuando se publican eventos en la cola.
- Sin embargo, la garantía de **Exactly-Once** se limita al proceso de **inserción en la cola**, no a la recepción por parte de los consumidores.

---

## 🟡 Google Cloud Pub/Sub

Google Cloud Pub/Sub es un servicio de mensajería escalable y asincrónico que conecta servicios usando un modelo publish-subscribe.

- Ofrece garantía de **Exactly-Once Delivery** para la publicación y procesamiento de mensajes.
- Internamente, utiliza técnicas como deduplicación basada en IDs de mensajes y control de reintentos automáticos.

---

## 🔵 Microsoft Azure Messaging

### 🔸 Azure Event Hubs
- Proporciona **Exactly-Once Delivery** en la salida de eventos cuando se consume y procesa mediante Azure Stream Analytics u otros servicios compatibles.

### 🔸 Azure Event Grid
- Usa un modelo de entrega **At-Least-Once**, con reintentos automáticos y respaldo en caso de error.
- El consumidor debe ser idempotente para manejar duplicaciones.

---

## ✅ Resumen Comparativo

| Broker            | Exactly Once | At Least Once | At Most Once | Notas Importantes |
|------------------|--------------|---------------|---------------|--------------------|
| Apache Kafka      | ✅ (entre topics) | ✅             | ✅             | Requiere configuración de transacciones |
| Amazon SQS (FIFO) | ✅ (en publicación) | ✅             | ❌             | Exactly-once solo en inserción |
| Google Pub/Sub    | ✅            | ✅             | ❌             | Detección de duplicados basada en ID |
| Azure Event Hubs  | ✅ (en salida) | ✅             | ❌             | Compatibilidad con herramientas de análisis |
| Azure Event Grid  | ❌            | ✅             | ❌             | Reintentos automáticos con posible duplicación |

---

## 🧠 Conclusión

Seleccionar la tecnología de mensajería adecuada implica un análisis cuidadoso de las necesidades del sistema:  
- ¿Puedes tolerar duplicados?  
- ¿Es crítico evitar pérdida de datos?  
- ¿Tu consumidor puede ser idempotente?

Cada plataforma tiene sus fortalezas y limitaciones. El diseño de tu arquitectura debe aprovechar las garantías que ofrece el broker elegido mientras mitigas sus riesgos.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)