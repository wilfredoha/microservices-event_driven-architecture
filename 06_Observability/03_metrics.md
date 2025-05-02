# 📊 03 - Metrics en Observabilidad para Microservicios

## 🔍 ¿Qué son las métricas?

Las **métricas** son valores numéricos agregados a lo largo del tiempo que describen el comportamiento, el estado o el rendimiento de un sistema. Son fundamentales para entender cómo se comportan los servicios y detectar anomalías o degradaciones antes de que afecten al usuario final.

Ejemplos:
- Tiempo promedio de respuesta.
- Porcentaje de uso de CPU.
- Cantidad de errores por minuto.
- Número de peticiones por segundo.

---

## ⚠️ Problemas de recolectar demasiadas métricas

Aunque recolectar métricas es esencial, hacerlo sin un enfoque definido puede tener efectos negativos:

- **Costoso**: El almacenamiento y procesamiento de métricas a gran escala puede aumentar significativamente los costos de infraestructura.
- **Sobrecarga de información**: Demasiados datos sin priorización pueden ocultar información crítica, dificultando el diagnóstico y la toma de decisiones.

Por eso, muchas organizaciones priorizan un conjunto reducido de métricas clave conocidas como **métricas doradas**.

---

## 🌟 Las 5 Métricas Doradas

Las 5 métricas más relevantes para observar la salud de un sistema, derivadas de los enfoques del **Google SRE Book** y del método **USE** de Brendan Gregg, son:

### 1. **Latencia**
Tiempo que tarda el sistema en responder a una solicitud. Una alta latencia puede indicar cuellos de botella o saturación del servicio.

### 2. **Tráfico**
Cantidad de solicitudes que el sistema maneja en un periodo de tiempo (por segundo, minuto, etc.). Esta métrica ayuda a entender la carga y el uso del sistema.

### 3. **Errores**
Porcentaje o cantidad absoluta de solicitudes fallidas. Es clave para detectar interrupciones, regresiones o fallas en servicios dependientes.

### 4. **Saturación**
Cuánto se acerca el sistema a su límite de capacidad. A menudo se mide con métricas como longitud de cola, tiempo de espera, o uso de CPU en picos.

### 5. **Utilización**
Proporción de uso de un recurso en relación con su capacidad total (por ejemplo, CPU, memoria o disco). Derivada del método **USE** (*Utilization, Saturation, Errors*), esta métrica indica si los recursos están siendo aprovechados eficientemente.

---

## ✅ Conclusión

Las métricas son fundamentales para evaluar el estado de sistemas distribuidos. En microservicios, donde el número de componentes es alto y la comunicación compleja, es crucial enfocarse en un conjunto pequeño pero poderoso de métricas.

Las **cinco métricas doradas** —**Latencia, Tráfico, Errores, Saturación y Utilización**— ofrecen una base sólida para monitorear y reaccionar ante problemas de forma proactiva.

A continuación, exploraremos **Distributed Tracing**, una herramienta crítica para entender los flujos de solicitudes entre servicios.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)