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

### 🔹 Modelado dimensional

- Creación de **dimensiones categóricas** derivadas de los códigos por capítulo de gasto  
  (ej. `1000 Servicios Personales`, `2000 Materiales y Suministros`, etc.).
- Estructuración del modelo para habilitar análisis por capítulo, tipo de gasto y origen del recurso.

### 🔹 Clasificación binaria del origen del recurso

Implementé una dimensión de origen para segmentar dinámicamente todo el modelo entre:

- **Gasto Etiquetado**: recursos federales condicionados.
- **Gasto No Etiquetado**: recursos propios de libre disposición.

### 🔹 Agrupaciones financieras estratégicas

Mapeé los capítulos tradicionales hacia **clasificaciones económicas avanzadas**:

- **Gasto Corriente**: operación e insumos.
- **Gasto de Capital**: inversión pública y bienes duraderos.
- **Servicio de la Deuda**: amortización e intereses.

---

## 📈 2. Análisis realizados y KPIs definidos

Desarrollé un **motor de cálculo en memoria** (simulando modelos DAX de Power BI) para generar métricas en tiempo real. Entre los principales análisis se incluyen:

### A. Ejecución y flujo de caja

- **% Avance Devengado**  
  \[
  \text{Avance} = \frac{\text{Devengado}}{\text{Modificado}}
  \]
  Con **semaforización RAG** para detectar ejecuciones atípicamente lentas.

- **Esfuerzo de Pago**  
  \[
  \text{Esfuerzo de Pago} = \frac{\text{Pagado}}{\text{Devengado}}
  \]
  Indicador diseñado para alertar sobre **posibles presiones de liquidez** o **rezagos de tesorería** (cuentas por pagar).

### B. Calidad y estructura del gasto

- **Índice de Esfuerzo Inversor**  
  \[
  \text{Esfuerzo Inversor} = \frac{\text{Gasto Capital Devengado}}{\text{Egresos Devengados Totales}}
  \]
  Permite evaluar si el gasto privilegia el **desarrollo de infraestructura** o el **consumo burocrático**.

- **Apalancamiento Operativo**  
  Relación de centavos gastados en operación por cada peso en nómina:
  \[
  \text{Apalancamiento Operativo} = \frac{\text{Materiales} + \text{Servicios Generales}}{\text{Servicios Personales}}
  \]

### C. Sostenibilidad y riesgos presupuestarios

- **Índice de Gasto Rígido**  
  Proporción del presupuesto comprometido en **compromisos ineludibles**:
  - Nómina
  - Deuda
  - Transferencias obligatorias  

  Su monitoreo ayuda a identificar el **margen de maniobra real** de la administración ante choques externos.

- **Concentración del Subejercicio**  
  Análisis del volumen financiero no ejecutado, distinguiendo si el “dinero en la mesa” proviene de:
  - Ahorros corrientes, o
  - Retrasos en obra pública (subejercicio en inversión).

---

## 💻 3. Interfaz y visualización de datos (UI/UX)

La aplicación está diseñada como una **Single Page Application (SPA)**, priorizando la **claridad financiera** y la **baja carga cognitiva** para el usuario.

### 🧭 Arquitectura de pestañas (tabs)

El tablero se organiza en 3 vistas analíticas:

1. **Resumen Ejecutivo**  
   Enfoque para alta dirección y pulso general del ejercicio.

2. **Estructura y Calidad**  
   Vista para análisis económico y composición del gasto.

3. **Sostenibilidad y Riesgo**  
   Orientada a órganos de control, auditores internos y tesorería.

### 🚨 Semaforización inteligente (Alertas RAG)

- Reglas de negocio integradas en los componentes visuales.
- Ejemplo: un **Esfuerzo de Pago < 90%** tiñe automáticamente el KPI de rojo y despliega la alerta  
  _“Riesgo de liquidez”_.

### 🔥 Mapa de calor de riesgo

- Matriz densa que evalúa el **subejercicio por capítulo**.
- Permite localizar de forma visual e inmediata **cuellos de botella operativos**.

---

## 🛠️ Stack tecnológico y habilidades demostradas

Este proyecto demuestra una integración completa entre **dominio de finanzas públicas** y **habilidades técnicas modernas**:

### 🧾 Domain expertise

- Finanzas Públicas y Presupuesto Municipal.
- Contabilidad Gubernamental bajo lineamientos **CONAC**.
- Análisis de estructura y ejercicio de egresos.

### 📊 Data & Analytics

- Modelado dimensional de datos.
- Definición de **KPIs lógicos y financieros**.
- Diseño de métricas de ejecución, calidad y sostenibilidad del gasto.

### 💻 Frontend & Visualización

- **React.js**
  - Componentes funcionales.
  - Hooks: `useState`, `useMemo` para optimización de cálculos en memoria.
- **Data Visualization**
  - **Recharts**: gráficos compuestos, de dona, barras apiladas dinámicas.
  - **Tailwind CSS**: diseño UI responsivo y moderno orientado a dashboards ejecutivos.

---

## 📬 Contacto

Si deseas conversar sobre cómo puedo aplicar estas habilidades analíticas y de desarrollo de visualizaciones en tu equipo o empresa, no dudes en contactarme:

- **Nombre:** Alonso Villalobos Lara  
- **LinkedIn:** https://www.linkedin.com/in/alonso-villalobos-lara-7297641b/  
- **Email:** alonsovl.logos88@gmail.com  
