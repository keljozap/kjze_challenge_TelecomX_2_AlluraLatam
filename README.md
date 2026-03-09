# �� TelecomX - Análisis y Predicción de Churn

Este repositorio contiene un análisis exhaustivo y la implementación de un pipeline completo de Machine Learning para predecir la evasión de clientes (Churn) en **TelecomX**, una empresa de telecomunicaciones.

## 🎯 Objetivo del Proyecto
Identificar patrones y factores clave que influyen en la decisión de los clientes de cancelar sus servicios, y construir modelos predictivos capaces de identificar futuros abandonos para proponer estrategias de retención basadas en datos.

## 📁 Estructura del Proyecto
*   `TelecomX_2_LATAM.ipynb`: Notebook principal con todo el código de extracción, limpieza, análisis, preprocesamiento y entrenamiento de modelos.
*   `TelecomX_Data.json`: (Fuente de datos) Dataset original en formato JSON anidado.

## 🛠️ Tecnologías Utilizadas
*   **Python 3.9+** (Entorno Virtual `uv`)
*   **Pandas & NumPy:** Manipulación y limpieza de datos matriciales.
*   **Matplotlib & Seaborn:** Visualización de relaciones bivariadas e importancia de características.
*   **Scikit-Learn:** Modelado Predictivo, Estandarización y Métricas.
*   **Imbalanced-Learn (SMOTE):** Balanceo de clases sintético.

## 🔍 Pasos Realizados
1.  **Extracción Interactiva:** Carga directa de datos desde repositorio remoto.
2.  **Transformación y Limpieza:** Aplanamiento de JSON, eliminación de IDs irrelevantes.
3.  **Análisis Exploratorio (EDA):** Matriz de Correlación y Boxplots para identificar el impacto del Tiempo de Contrato (`Tenure`) y Gasto Total (`TotalCharges`).
4.  **Preprocesamiento de Árbol (Feature Engineering):** 
    * Transformación de variables categóricas a numéricas (`One-Hot Encoding`).
    * Aplicación de **SMOTE** para balancear el 100% las clases de Churn.
    * Estandarización de las características para modelos de distancia (`StandardScaler`).
5.  **Modelado de Machine Learning:** Split 70/30 para entrenamiento de modelos de **Regresión Logística** y **Random Forest Classifier**.

## 🚀 Cómo Ejecutar
1. Clonar este repositorio.
2. Asegurar tener [uv](https://docs.astral.sh/uv/) instalado.
3. Instalar las dependencias necesarias:
   ```bash
   uv add pandas matplotlib seaborn scikit-learn imbalanced-learn
   ```
4. Abrir el archivo `TelecomX_2_LATAM.ipynb` en Jupyter Lab/Notebook o VS Code.
5. Ejecutar todas las celdas secuencialmente.

## 💡 Principales Conclusiones y Propuestas (Insights de los Modelos)
Al evaluar e inspeccionar el interior del Bosque Aleatorio (Random Forest) y la Regresión Logística, extrajimos los siguientes hallazgos definitivos:

*   🔴 **El Detonante Principal:** Los contratos **mensuales (Month-to-month)** son el factor de riesgo absoluto. 
*   🔴 **La Anomalía Premium:** Los usuarios con **Fibra Óptica** presentan una tasa de abandono anormal, muy superior a los que usan la conexión básica DSL. Se recomienda enviar al equipo de ingeniería técnica a revisar la infraestructura de este servicio vital.
*   🟢 **El Ancla de Salvación:** La antigüedad en la empresa (`Tenure`) y poseer paquetes de `Online Security` fungen en nuestros modelos como los escudos más grandes contra la cancelación. Se recomienda realizar campañas estratégicas (descuentos o trials gratuitos) para amarrar clientes nuevos a contratos mínimos de 1 año.

---
*Desarrollado para el Challenge de Data Science LATAM.*
