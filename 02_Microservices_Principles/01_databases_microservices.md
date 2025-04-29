# 🛢️ Databases in Microservices Architecture

Una decisión fundamental en la arquitectura de microservicios es cómo gestionar los datos.  
Un principio ampliamente adoptado es **"Database per Microservice"**, es decir, cada microservicio posee y administra su propia base de datos.

---

## 🎯 Motivation for Database per Microservice

- **Autonomía Total:** Cada microservicio puede evolucionar su modelo de datos de forma independiente sin coordinar cambios con otros equipos.
- **Escalabilidad Independiente:** Permite escalar solo las bases de datos de los microservicios que lo requieran, optimizando recursos y costos.
- **Aislamiento de Fallos:** Problemas en la base de datos de un microservicio no afectan directamente la operación de otros servicios.
- **Especialización Tecnológica:** Cada microservicio puede elegir el tipo de base de datos (SQL, NoSQL, In-Memory) que mejor se adapte a sus necesidades específicas (**Polyglot Persistence**).

---

## 🌟 Benefits of Database per Microservice Principle

| Beneficio                          | Descripción |
|-------------------------------------|-------------|
| Independencia del ciclo de vida     | Los servicios pueden ser desarrollados, desplegados y escalados de manera independiente. |
| Mejora de la resiliencia            | Fallos en la base de datos de un servicio no se propagan a toda la arquitectura. |
| Libertad tecnológica                | Cada servicio puede utilizar el motor de base de datos más adecuado (PostgreSQL, MongoDB, Redis, etc.). |
| Simplificación del control de acceso | Cada microservicio controla su propio modelo de seguridad y acceso a datos. |

---

## ⚠️ Downsides of Database per Microservice

Aunque ofrece muchas ventajas, el enfoque de "una base de datos por microservicio" también introduce ciertos desafíos:

### 🔗 Dificultad en los Joins
- Las bases de datos están separadas, por lo que no se pueden realizar **joins directos** entre tablas de diferentes microservicios.
- Es necesario combinar datos a nivel de **servicio** o en la **capa de agregación**.

### 🕒 Mayor Latencia
- Cuando un flujo de negocio necesita datos de múltiples microservicios, se deben realizar varias llamadas de red, aumentando la latencia.
- Soluciones como **materialized views** o **cachés distribuidos** pueden mitigar este problema.

### 🛠️ Complejidad en la Consistencia
- Mantener la **consistencia transaccional** entre múltiples bases de datos es difícil.
- En vez de transacciones distribuidas, se utilizan patrones como **Eventual Consistency**, **Saga** o **Transactional Outbox**.

### 📊 Mayor Costo Operacional
- Se incrementa la carga de trabajo en la gestión, monitoreo, respaldos y seguridad de múltiples bases de datos.

### 🔄 Duplicación de Datos
- Para mejorar el rendimiento y reducir la latencia, es común duplicar datos entre microservicios, lo que introduce retos de sincronización.

---

## 🧠 Conclusión

El patrón **Database per Microservice** es clave para lograr verdadera autonomía y escalabilidad en una arquitectura de microservicios.  
Sin embargo, introduce nuevos desafíos de complejidad, latencia y consistencia que deben ser abordados cuidadosamente mediante patrones complementarios y buenas prácticas de diseño de sistemas distribuidos.

> ⚖️ **Como toda decisión arquitectónica, se debe evaluar cuidadosamente el contexto y los requisitos del sistema antes de adoptar este enfoque.**

---

[Menú Principal](https://github.com/wilfredoha/microservices-event_driven-architecture)