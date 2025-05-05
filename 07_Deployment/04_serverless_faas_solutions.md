# ☁️ 04 - Serverless FaaS: Soluciones

## 🧩 Despliegue Serverless para Microservicios usando FaaS

El modelo **Function as a Service (FaaS)** permite ejecutar funciones de forma altamente escalable, eliminando la necesidad de administrar servidores. A continuación, se presentan las principales soluciones FaaS ofrecidas por los principales proveedores cloud.

---

## 🟧 Amazon Web Services (AWS)

### 🔧 AWS Lambda

AWS Lambda es un servicio de cómputo **serverless y orientado a eventos** que permite ejecutar código para prácticamente cualquier tipo de aplicación o backend, **sin necesidad de aprovisionar o administrar servidores**.

- Puede ser activado por **más de 200 servicios de AWS** (como S3, DynamoDB, API Gateway) y aplicaciones SaaS.
- Compatible con múltiples lenguajes como Python, Node.js, Java, Go, C#, entre otros.
- Se **cobra únicamente por el tiempo de ejecución y la memoria utilizada**, bajo el modelo pay-as-you-go.

**Casos de uso comunes**:
- Procesamiento en tiempo real (logs, imágenes, streams)
- Backend para APIs
- Automatización de tareas operativas

---

## 🟦 Google Cloud Platform (GCP)

### 🔧 Cloud Functions

GCP Cloud Functions permite ejecutar funciones pequeñas de manera aislada **sin administrar servidores ni contenedores**. Es ideal para arquitecturas event-driven en la nube de Google.

- Escalabilidad automática.
- Integración nativa con otros servicios como Cloud Pub/Sub, Firebase, Cloud Storage, entre otros.
- Modelo de precios **basado en uso real**, con facturación por número de invocaciones, duración de la función y memoria asignada.

**Casos de uso comunes**:
- Procesamiento de archivos subidos a Cloud Storage
- Reacción a eventos de bases de datos
- Automatización de flujos de trabajo

---

## 🟪 Microsoft Azure

### 🔧 Azure Functions

Azure Functions es un servicio serverless bajo demanda que permite **enfocarse exclusivamente en el código**, dejando la gestión de infraestructura a la plataforma de Azure.

- Compatible con múltiples lenguajes (C#, JavaScript, Python, Java, PowerShell, etc.).
- Permite programación basada en eventos (triggers) y enlaces automáticos con otros servicios.
- Ofrece **modos de ejecución flexibles**: consumo (autoescalado y pago por uso) o dedicado (usando un App Service Plan o Kubernetes).

**Casos de uso comunes**:
- Automatización de tareas dentro de flujos de integración y entrega continua (CI/CD)
- Backend sin servidor para aplicaciones móviles o web
- Procesamiento de datos en streaming

---

## 🧮 Comparativa General

| Proveedor         | Solución         | Activadores principales                | Lenguajes soportados                   | Modelo de precios             |
|-------------------|------------------|----------------------------------------|----------------------------------------|-------------------------------|
| AWS               | AWS Lambda       | +200 servicios AWS, eventos externos   | Node.js, Python, Go, Java, C#, Ruby... | Pay per request + compute     |
| Google Cloud      | Cloud Functions  | Cloud Pub/Sub, Storage, Firestore      | Node.js, Python, Go, Java, .NET        | Pay-as-you-go                 |
| Microsoft Azure   | Azure Functions  | HTTP, Event Grid, Cosmos DB, Queue     | C#, JavaScript, Python, Java, PowerShell | Pay per execution + time      |

---

## 📝 Conclusión

FaaS es una herramienta poderosa dentro de las arquitecturas modernas de microservicios. Con soluciones maduras de AWS, GCP y Azure, las organizaciones pueden elegir el proveedor que mejor se ajuste a sus necesidades técnicas, de integración y de costos. La elección debe considerar aspectos como el ecosistema del proveedor, los lenguajes compatibles y el modelo operativo del equipo.

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/03_serverless_faas.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/05_containers_in_dev_test_prod.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)