# 🎬 Libreria de Peliculas – OWASP Security Testing

![Proyecto Libreria de Peliculas](PruebasOWASP/images/Captura%20de%20pantalla%202025-12-25%20140839.jpg)


Proyecto de **librería de películas** desarrollado con el objetivo de **analizar y demostrar vulnerabilidades de seguridad** basadas en el **OWASP Top 10**, enfocándose específicamente en las pruebas **A1, A2 y A3**.

Este repositorio incluye:
- Implementación de un sistema básico de películas
- Pruebas de seguridad controladas
- Evidencia mediante **capturas de pantalla**
- Análisis de impacto y resultados

---

## 🎯 Objetivo del Proyecto

Evaluar vulnerabilidades comunes en aplicaciones web utilizando una aplicación de ejemplo (Libreria de Peliculas), aplicando pruebas de seguridad sobre:

- **A1 – Broken Access Control**
- **A2 – Cryptographic Failures**
- **A3 – Injection**

El propósito es **identificar, explotar y documentar** dichas vulnerabilidades con fines educativos. Se usara Postman para las pruebas.

---

## 🧪 Pruebas de Seguridad Implementadas

### 🔐 A1 – Broken Access Control
Se evaluara si un usuario puede acceder, crear modificar o eliminar recursos de la base de datos sin permisos, usando Postman.

📸 **Evidencia:** 

![A1 - Acceso no autorizado](PruebasOWASP/images/Captura%20de%20pantalla%202025-12-25%20142054.jpg)

Esto para una aplicacion que no requiere una autenticacion previa es aceptable, pero en caso de manejar autenticaciones y tokens es necesario manejar roles dentro del aplicativo para evitar la creacion, modificacion o eliminacion de datos sensibles por usuarios no autorizados.

---

### 🔑 A2 – Cryptographic Failures
Se analizan fallos relacionados con:
- Headers de seguridad
- Falta de cifrado en información crítica


📸 **Prueba 1:** Capturas de inspeccion de headers de seguridad

![A2 - Headers](PruebasOWASP/images/Captura%20de%20pantalla%202025-12-25%20143205.jpg)

Se valida los headers de seguridad correctamente.

---

📸 **Prueba 2:** Capturas de intentos de accesos a archivos de configuracion

![A2 - Acceso no permitido a archivos sensibles](PruebasOWASP/images/Captura%20de%20pantalla%202025-12-25%20144101.jpg)

✅ Se observa que retorna error 404 al intentar acceder a archivos sensibles.

---

### 💉 A3 – Injection
Se realizan pruebas de inyección para comprobar vulnerabilidades como:
- SQL Injection
- Manipulación de entradas del usuario
- Falta de validación y sanitización

Como prueba inicial se realizara un SQL injection basico como mandar una comilla simple en el parametro de busqueda.
📸 **Evidencia:** Capturas demostrando SQL Injection basico.

![A3 - SQL Injection basico](PruebasOWASP/images/Captura%20de%20pantalla%202025-12-25%20161200.jpg)

✅ Retorna codigo 200.

---




## 📸 Resultados y Evidencia

⚠️ A1: Se requiere autenticacion para evitar la creacion, modificacion y eliminacion de datos por usuarios no autorizados.
✅ A2: Headers de seguridad correctos. No se puede acceder a archivos sensibles por comandos, retorna error 404.
✅ A3: No retorna error de base de datos ante prueba basica de SQL Injection.

