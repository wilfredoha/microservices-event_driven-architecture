# ☸️ 06 - Kubernetes para Microservicios

## 🚀 Introducción a la Orquestación de Contenedores

En aplicaciones modernas basadas en microservicios y contenedores, **necesitamos herramientas que gestionen de forma eficiente el ciclo de vida de cientos o miles de contenedores**. Aquí es donde entra la orquestación de contenedores.

### ¿Qué es un orquestador de contenedores?

Es una herramienta que actúa como el **“sistema operativo” de tu plataforma de microservicios**, encargándose de:

- 📦 **Automatización del despliegue** de contenedores.
- 🧠 **Asignación de recursos** basada en requerimientos y disponibilidad.
- ❤️ **Monitoreo de salud** de los servicios.
- 🔁 **Auto-recuperación (Self-healing)**: reinicia contenedores fallidos o migra cargas.
- 📊 **Bin-packing**: asignación eficiente de cargas de trabajo para optimizar el uso de recursos.
- 🔄 **Balanceo de carga** entre réplicas de servicios.
- 📈 **Escalado automático** de servicios según demanda.
- 🌐 **Conectividad entre contenedores** mediante redes virtuales.

Kubernetes es el estándar de facto en este campo.

---

## ☸️ Kubernetes: El Orquestador de Contenedores Más Usado

Kubernetes (K8s) es una plataforma open-source diseñada por Google para automatizar el despliegue, escalado y operación de aplicaciones en contenedores. Es altamente extensible y soportado por todos los principales proveedores de nube (AWS, GCP, Azure).

---

## 🏗️ Arquitectura de Orquestación de Contenedores (Kubernetes)

Kubernetes sigue una arquitectura de tipo **Master-Worker**:

### 🧠 Plano de control (Control Plane)
- **API Server**: punto de entrada para comandos y peticiones.
- **Scheduler**: decide en qué nodo correr cada contenedor.
- **Controller Manager**: ejecuta procesos de control que mantienen el estado deseado.
- **etcd**: almacén de claves-valor que guarda el estado del clúster.

### 🔧 Nodos (Workers)
Cada nodo corre:
- **Kubelet**: agente que ejecuta contenedores y se comunica con el plano de control.
- **Container Runtime**: como containerd o CRI-O, para ejecutar contenedores.
- **Kube-proxy**: maneja el tráfico de red hacia y desde los contenedores.

### 🧱 Recursos clave de Kubernetes
- **Pod**: unidad mínima de ejecución (uno o más contenedores).
- **Deployment**: asegura que haya un número deseado de pods ejecutándose.
- **Service**: expone pods como un servicio estable y balanceado.
- **Namespace**: separa entornos y recursos lógicamente.

---

## 🎯 Beneficios de Kubernetes para Microservicios

- Estandariza el **despliegue y gestión** de servicios distribuidos.
- Facilita el **desarrollo ágil y escalado horizontal**.
- Permite aplicar patrones modernos como **circuit breakers**, **blue/green deployments**, **service mesh**, entre otros.
- Compatible con observabilidad, seguridad, y políticas de red avanzadas.

---

## 📌 Conclusión

Kubernetes es el pilar central en arquitecturas modernas de microservicios que utilizan contenedores. Su robustez y ecosistema permiten automatizar operaciones complejas, aumentar la resiliencia de los servicios y mejorar la eficiencia operativa en entornos distribuidos.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)