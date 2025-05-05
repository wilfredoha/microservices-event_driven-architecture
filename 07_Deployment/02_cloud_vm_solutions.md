# ☁️ 02 - Cloud VM Solutions

## 🧩 Soluciones de Máquinas Virtuales Multi-Tenant en la Nube

### 🔹 Amazon EC2 (Elastic Compute Cloud)
Amazon EC2 ofrece capacidad de cómputo escalable bajo demanda, mediante **servidores virtuales (instances)**.

- Soporta múltiples tipos de instancias optimizadas para distintas cargas de trabajo: uso general, cómputo intensivo, memoria optimizada, almacenamiento denso, entre otros.
- Alta escalabilidad y flexibilidad.
- Amplio ecosistema de herramientas de administración, monitoreo y seguridad.

### 🔹 Google Cloud Compute Engine
Compute Engine permite la creación de máquinas virtuales personalizadas sobre la infraestructura de Google.

- Soporta múltiples arquitecturas (x86, ARM).
- Tipos de instancias especializados: **Scale-Out**, uso general, memoria ultra-alta, cómputo intensivo, optimizadas con aceleradores (GPU/TPU), entre otras.
- Altamente configurable, permite elegir familia de CPU, tipo de disco y ubicación regional.

### 🔹 Microsoft Azure Virtual Machines
Azure permite crear máquinas virtuales Linux y Windows con rapidez y flexibilidad.

- Varias series de VMs según el propósito:
  - **B-series** (burstables)
  - **D-series** (uso general)
  - **E-series** (optimizada para memoria)
  - **F-series** (optimizada para cómputo)
  - **Lsv2-series** (optimizada para almacenamiento)
  - **N-series** (con soporte GPU)
- Integración nativa con otros servicios Azure como Azure Monitor, Defender, y Azure Backup.

---

## 🛡️ Soluciones de Dedicated Hosts y Single-Tenant Virtual Machines

### 🔸 AWS Dedicated EC2 Instances
- Instancias EC2 dedicadas que se ejecutan en hardware reservado exclusivamente para un único cliente (una cuenta de AWS).
- Aislamiento físico de instancias entre cuentas diferentes.
- **Nota:** pueden compartir hardware con otras instancias de la misma cuenta si no se configura un host dedicado.

### 🔸 Amazon EC2 Dedicated Hosts
- Servidores físicos enteros dedicados exclusivamente para tu uso.
- Útiles para cumplir requerimientos de cumplimiento normativo, licenciamiento específico (BYOL) o control de afinidad con el hardware.
- Se pueden ejecutar múltiples instancias EC2 en un mismo host dedicado.

### 🔸 GCP Sole-Tenant Nodes
- Acceso exclusivo a un servidor físico completo en Google Cloud.
- Puedes ejecutar múltiples VMs dentro de un solo nodo dedicado.
- Diseñado para cumplir con políticas estrictas de seguridad, licenciamiento y aislamiento.

### 🔸 Azure Dedicated Hosts
- Servidores físicos dedicados para una organización específica.
- Permite ejecutar una o más VMs sin compartir el host con otros clientes.
- Ideal para cargas sensibles, cumplimiento normativo y necesidades de aislamiento total.

---

## 📊 Comparativa de Opciones de VM en la Nube

| Tipo de VM                     | Costo         | Seguridad                         | Performance                      |
|-------------------------------|---------------|-----------------------------------|----------------------------------|
| **Multi-Tenant VM**           | Bajo          | Aislada virtualmente              | Variable (riesgo de noisy neighbor) |
| **Single-Tenant VM**          | Medio - Alto  | Aislamiento físico parcial        | Más consistente                  |
| **Dedicated Host**            | Alto          | Aislamiento total a nivel de host | Máximo control y rendimiento     |

---

## ✅ Conclusión

La elección entre instancias multi-tenant, single-tenant o dedicated hosts depende de factores como el presupuesto, los requisitos de seguridad, las regulaciones de cumplimiento y la sensibilidad de la carga de trabajo. Los servicios ofrecidos por AWS, Google Cloud y Azure cubren una amplia gama de necesidades para entornos empresariales y altamente regulados.

---

[Anterior](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/01_cloud_virtual_machines.md)   [Siguiente](https://github.com/wilfredoha/microservices-event_driven-architecture/blob/main/07_Deployment/03_serverless_faas.md)

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)