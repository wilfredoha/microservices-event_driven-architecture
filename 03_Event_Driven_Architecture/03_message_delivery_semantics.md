# 📦 Message Delivery Semantics in Event-Driven Architecture

El manejo correcto de la entrega de mensajes es una preocupación central en los sistemas distribuidos y especialmente en arquitecturas orientadas a eventos. Las garantías de entrega determinan la confiabilidad, consistencia y rendimiento de un sistema.

---

## ❗ Problema de entrega en el modelo Request-Response

En arquitecturas tradicionales de request-response, los problemas de entrega suelen presentarse cuando:

- La solicitud llega, pero la respuesta no (por timeout o error de red).
- El cliente reintenta, causando operaciones duplicadas si el backend no es idempotente.
- La respuesta llega, pero el cliente ya ha cancelado la operación o no la puede procesar.

Este modelo está estrechamente acoplado a la disponibilidad inmediata de ambos extremos, lo que limita la tolerancia a fallos y puede provocar errores difíciles de manejar.

---

## ❗ Problemas de entrega en Event-Driven Architecture

En arquitecturas basadas en eventos, los problemas de entrega surgen debido a la asincronía entre productor, message broker y consumidor:

- El mensaje puede **perderse** si no se almacena correctamente en el broker.
- El mensaje puede ser **consumido varias veces** si el procesamiento falla y se reintenta sin control.
- El consumidor puede fallar antes de confirmar la recepción, generando duplicaciones.
- Existen diferencias en cómo los brokers implementan la entrega, generando **semánticas distintas** de fiabilidad.

---

## 📌 Semánticas de entrega

Existen tres niveles principales de garantía de entrega en sistemas de mensajería:

### ✅ At-Most-Once

- El mensaje se entrega **como máximo una vez**.
- Si ocurre un fallo durante la entrega, **se pierde el mensaje**.
- No hay reintentos automáticos.
- ✔️ *Ventajas:* mínima latencia y sobrecarga.
- ❌ *Desventajas:* posibilidad de pérdida de datos.
- 🧠 *Uso recomendado:* sistemas donde los datos no son críticos y la pérdida es tolerable (e.g., logs de baja prioridad).

---

### ✅ At-Least-Once

- El mensaje se entrega **al menos una vez**.
- Si no se confirma la entrega, el broker reintentará.
- Puede causar **duplicación de eventos** si el consumidor no es idempotente.
- ✔️ *Ventajas:* garantiza que el mensaje llegará.
- ❌ *Desventajas:* puede requerir lógica adicional para manejar duplicados.
- 🧠 *Uso recomendado:* cuando **la pérdida de datos no es aceptable**, pero se puede manejar la duplicación.

---

### ✅ Exactly-Once

- El mensaje se entrega **exactamente una vez** al consumidor, sin pérdida ni duplicación.
- ✔️ *Ventajas:* máxima fiabilidad y consistencia.
- ❌ *Desventajas:* muy difícil de implementar, alta sobrecarga y latencia.
- Requiere coordinación entre productor, broker y consumidor (transacciones distribuidas, logs de compensación, idempotencia estricta).
- 🧠 *Uso recomendado:* sistemas altamente críticos como procesamiento financiero o actualización de inventarios.

---

## 🧠 Conclusión

La semántica de entrega elegida impacta directamente en la arquitectura, el diseño del sistema y la experiencia del usuario final.  
Elegir entre `at-most-once`, `at-least-once` y `exactly-once` depende de:

- La criticidad de los datos.
- La tolerancia al retraso o duplicación.
- La complejidad y costo aceptable para el sistema.

En la práctica, **at-least-once con lógica de idempotencia** suele ser un equilibrio razonable entre confiabilidad y complejidad.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)