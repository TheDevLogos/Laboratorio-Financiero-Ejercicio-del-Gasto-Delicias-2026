# 📊 Laboratorio de Finanzas Públicas: Análisis de Egresos Municipales

Bienvenido a mi **Laboratorio de Estructura, Calidad y Sostenibilidad del Gasto Público**.  
En este repositorio presento una solución interactiva de Business Intelligence diseñada para transformar el **Estado Analítico del Ejercicio del Presupuesto de Egresos (formato CONAC)** en una herramienta dinámica para la toma de decisiones estratégicas.

---

## 🎯 Objetivo del proyecto

El objetivo principal de este desarrollo es ir más allá del tradicional seguimiento de “cuánto se ha gastado” para responder a preguntas críticas de finanzas públicas:

- ¿En qué se está gastando?
- ¿Existe riesgo de subejercicio?
- ¿Cuál es nuestro margen de maniobra financiero real?

Para lograrlo, diseñé y desarrollé un **dashboard interactivo con React**, procesando datos estructurados a partir de **reportes financieros oficiales**.

---

## ⚙️ 1. Proceso de integración y transformación de datos

El insumo original consistía en **reportes en PDF** y **archivos planos (CSV/Excel)** correspondientes a los egresos municipales (`egresos_integrado.csv`). A partir de ellos, construí un modelo de datos escalable mediante:

### 🔹 Extracción y limpieza

- Procesamiento de registros crudos provenientes de reportes oficiales.
- Eliminación de jerarquías anidadas complejas.
- Aplanamiento de la información en una **Tabla de Hechos transaccional**.

