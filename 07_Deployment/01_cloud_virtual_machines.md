# ☁️ 01 - Cloud Virtual Machines

## 🖥️ ¿Qué es una Máquina Virtual en la Nube?

Una **máquina virtual (VM)** en la nube es una instancia computacional que se ejecuta sobre hardware físico compartido mediante un hipervisor. Este modelo se conoce como **multi-tenancy**, ya que varios clientes pueden compartir los mismos recursos físicos (CPU, memoria, almacenamiento), aunque en entornos virtuales aislados.

### 🎯 Beneficios de Multi-Tenancy
- **Eficiencia de costos:** Recursos compartidos → menores precios.
- **Escalabilidad rápida:** Fácil de aprovisionar o eliminar.
- **Mantenimiento simplificado:** La responsabilidad del hardware recae en el proveedor cloud.

### ⚠️ Desventajas
- **Riesgo de "noisy neighbor":** El rendimiento de una VM puede verse afectado si otras VMs en el mismo host consumen excesivamente los recursos.
- **Seguridad compartida:** Aunque aisladas, las VMs aún corren en el mismo hardware físico.
- **Variabilidad de rendimiento:** Menor control sobre latencia y throughput.

---

## 🛡️ Dedicated Hosts e Instancias Single-Tenant

### 🔒 Instancias Single-Tenant
- Corren en un servidor físico exclusivo para un solo cliente.
- Aislamiento total de otras organizaciones.
- Ideal para regulaciones estrictas de seguridad y cumplimiento normativo.

### 🧱 Dedicated Hosts
- Provisión de un servidor físico completo, sobre el cual el cliente puede lanzar múltiples VMs.
- Permite control completo del host (licenciamiento BYOL, afinidad con hardware, etc.).
- Útil para software que requiere licencias físicas específicas o configuraciones personalizadas.

### ❗Desventajas
- **Costo significativamente más alto.**
- **Menor flexibilidad:** Recursos fijos, menos escalabilidad automática.
- **Mayor responsabilidad operativa:** El cliente puede ser responsable de configuraciones a bajo nivel.

---

## 📊 Comparativa: Multi-Tenant vs Single-Tenant vs Dedicated Host

| Característica     | Multi-Tenant VM               | Single-Tenant VM                 | Dedicated Host                        |
|--------------------|-------------------------------|----------------------------------|----------------------------------------|
| **Costo**          | Bajo                          | Medio - Alto                     | Alto                                   |
| **Seguridad**      | Aislada virtualmente          | Mayor aislamiento físico         | Aislamiento completo a nivel de host   |
| **Performance**    | Variable (noisy neighbor)     | Más consistente                  | Máximo control y rendimiento predecible|
| **Escalabilidad**  | Alta (on-demand)              | Media (más lenta)               | Baja (hardware fijo)                   |
| **Casos de uso**   | General, apps web, staging    | Producción crítica, cumplimiento | Software licenciado, workloads sensibles|

---

## ✅ Conclusión

Las máquinas virtuales en la nube ofrecen diferentes niveles de aislamiento, costo y rendimiento según el tipo de implementación. Para cargas de trabajo generales y económicas, las **multi-tenant VMs** son la mejor opción. Para entornos regulados o sensibles, las **single-tenant VMs** o los **dedicated hosts** ofrecen un mayor control y seguridad a un costo más elevado.

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)