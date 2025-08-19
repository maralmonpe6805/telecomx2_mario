### PREDICCION DE CANCELACION DE CLIENTES EN TELECOM X

### OBJETIVO:

Proyecto mediante el cual se busca predecir qué clientes tienen mayor probabilidad de cancelar su servicio en la empresa ficticia Telecom X. Se parte de un conjunto de datos de clientes y se construyen modelos de machine learning para anticipar el churn y entender los factores que más influyen en él.

### CONTENIDO:

- Análisis exploratorio de los datos
- Preprocesamiento y limpieza
- Ingeniería de variables
- Balanceo de clases con SMOTE
- Comparación de modelos de clasificación
- Interpretación de variables clave
- Estrategias de retención sugeridas
  

### 1. DATASET:

El dataset incluye información de más de 7.000 clientes de Telecom X, con variables como:

- Datos personales (género, edad, si tiene pareja o dependientes)
- Antigüedad como cliente (`tenure`)
- Servicios contratados (internet, telefonía, soporte, etc.)
- Métodos de pago y tipo de contrato
- Variables derivadas como monto mensual (`Monthly`) y cantidad de servicios
- Columna objetivo: `Churn` (1 si canceló, 0 si sigue activo)

### 2. PROCESAMIENTO:

- Se eliminaron columnas redundantes por alta correlación (`Total`, `MonthlyGroup`, `Cuentas_Diarias`)
- Se codificaron variables categóricas con `get_dummies`
- Se aplicó `StandardScaler` a variables numéricas continuas para modelos sensibles a escala
- Se utilizó **SMOTE** para balancear las clases antes de entrenar

### 3. MODELOS EVALUADOS:

Se entrenaron y compararon los siguientes modelos:

- **Regresión Logística**
- **Random Forest**
- **KNN**
- **XGBoost**

Se evaluaron con métricas como **Accuracy**, **Precision**, **Recall**, **F1-score** y **ROC AUC**.

**Modelo campeón:** Regresión Logística (mejor F1 y AUC)

### 4. VARIABLES MAS RELEVANTES:

- `Contract_Two year`: contratos largos reducen fuertemente el churn
- `tenure`: clientes con mayor antigüedad tienden a quedarse
- `InternetService_Fiber optic`: clientes con fibra óptica cancelan más
- `OnlineSecurity`, `TechSupport`: asociados a mayor retención
- `Monthly`: cuanto más paga un cliente, más propenso es a cancelar
- `PaymentMethod_Electronic check`: se asocia a mayor tasa de cancelación

### 5. ESTRATEGIAS DE RETENCION SUGERIDAS:

- Incentivar contratos a largo plazo
- Ofrecer servicios adicionales que aumenten el valor percibido
- Mejorar la experiencia de usuarios con fibra óptica
- Implementar beneficios personalizados para clientes nuevos con pagos altos
- Evaluar cambios en opciones de pago menos asociadas a fidelidad

