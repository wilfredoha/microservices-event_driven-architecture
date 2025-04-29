# 🧬 The DRY Principle in Microservices and Shared Libraries

En la arquitectura de microservicios, el principio **DRY (Don't Repeat Yourself)** promueve la reutilización de código para evitar duplicaciones innecesarias. Sin embargo, aplicar este principio en sistemas distribuidos requiere un enfoque diferente al de arquitecturas monolíticas.

---

## 📌 What is DRY and Why It Matters?

**DRY (Don't Repeat Yourself)** es un principio de diseño que busca eliminar la duplicación de lógica y datos.  
Su objetivo es:

- Reducir errores y mantener consistencia.
- Facilitar el mantenimiento del código.
- Mejorar la productividad del desarrollo.

En sistemas monolíticos, aplicar DRY es relativamente simple usando librerías compartidas.  
Pero en microservicios, **reutilizar código mediante shared libraries puede ser contraproducente**.

---

## ⚠️ Challenges of DRY and Shared Libraries in Microservices

### 🔗 Tight Coupling
- Las shared libraries crean dependencias fuertes entre microservicios.
- Las decisiones de diseño en una librería impactan múltiples servicios.

### 🔄 Rebuild, Retest, Redeploy
- Un pequeño cambio en una librería compartida obliga a:
  - Recompilar todos los servicios dependientes.
  - Ejecutar pruebas completas.
  - Redistribuir servicios innecesariamente.

### 🐛 Propagación de Errores
- Un bug o vulnerabilidad en una shared library afecta a todos los servicios que la usan.

### 🧩 Dependency Hell
- Dificultad para mantener compatibilidad entre versiones.
- Problemas al actualizar librerías cuando múltiples servicios usan distintas versiones.

---

## 🔄 Alternatives to Shared Libraries in Microservices

### 🚫 Shared Business Logic
- Compartir lógica de negocio a través de librerías suele indicar una **mala separación de límites**.
- ✅ Alternativas:
  - **Reevaluar los boundaries del dominio**.
  - **Extraer un nuevo microservicio** que encapsule esa lógica.

### 📦 Common Data Model for Communication

- Es válido compartir un **modelo de datos común** para facilitar la interoperabilidad.
  - Usar una librería específica para ese propósito.
  - Generar código automáticamente a partir de contratos.

> 🔐 Estos contratos deben ser **versionados** y considerados inmutables una vez publicados.

### ✍️ Código que está bien duplicar

No todo debe ser DRY. En microservicios, **duplicar ciertos fragmentos de código puede ser la mejor decisión**:

| Tipo de Código | ¿Duplicable? | Razón |
|----------------|---------------|--------|
| Métodos utilitarios (helpers, fechas, cadenas, etc.) | ✅ | Cambian con frecuencia, evitan dependencia cruzada. |
| Validaciones ligeras | ✅ | Bajo riesgo, alta autonomía. |
| Lógica de presentación | ✅ | Aislada por frontend. |

### ✅ DRY sin librerías compartidas

| Estrategia           | Descripción |
|----------------------|-------------|
| Sidecar Pattern      | Extraer funcionalidad reutilizable a un contenedor adjunto (autenticación, logging, etc.). |
| Shared Library autónoma | Crear una librería que no dependa de otros servicios ni frameworks, fácil de versionar y testear. |

---

## 🔁 Sharing or Duplicating Data Across Microservices

- **Cada microservicio debe ser dueño de su propio modelo de datos.**
- Compartir datos es válido **solo si hay un claro "source of truth"**.
- En microservicios, la consistencia es **eventual**, no transaccional.
- Copiar datos es aceptable si está bien justificado, y si se mantienen sincronizados mediante eventos.

---

## 🧠 Conclusión

Aunque el principio **DRY** sigue siendo valioso, en una arquitectura de microservicios su aplicación debe hacerse con criterio.  
Evitar duplicación **a toda costa puede generar más acoplamiento y rigidez** que beneficios.  
Evalúa cuándo compartir, cuándo duplicar y cuándo externalizar funcionalidades reutilizables como servicios o sidecars.

> 🔧 **En microservicios, "WET" (Write Everything Twice) puede ser preferible si te da autonomía, resiliencia y velocidad.**

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)