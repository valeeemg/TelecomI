📊 Informe de Análisis de Evasión de Clientes (Churn)

La evasión de clientes, conocida como Churn, es un indicador clave en empresas de telecomunicaciones, ya que refleja la cantidad de clientes que cancelan su servicio en un determinado periodo. La pérdida de clientes puede afectar significativamente los ingresos de la empresa, además de incrementar los costos asociados a la adquisición de nuevos usuarios.

El objetivo de este análisis es explorar y comprender los factores que influyen en la cancelación del servicio por parte de los clientes, utilizando un conjunto de datos proporcionado por la empresa TelecomX. A través de técnicas de limpieza de datos, transformación de variables y análisis exploratorio, se busca identificar patrones en el comportamiento de los clientes que permitan detectar posibles causas de evasión.

Este proceso permite obtener información valiosa para la toma de decisiones estratégicas, orientadas a mejorar la retención de clientes y reducir la tasa de cancelación del servicio.

# Limpieza y Tratamiento de Datos

El proceso de preparación de los datos comenzó con la importación del archivo en formato JSON utilizando la biblioteca Pandas en Python. Posteriormente se realizó una inspección inicial de la estructura del conjunto de datos mediante funciones como head(), info() y columns() para comprender la organización de las variables.

Durante esta revisión se identificó que algunas columnas contenían estructuras anidadas en forma de diccionarios, específicamente las columnas relacionadas con información del cliente, servicios telefónicos, servicios de internet y datos de facturación. Para poder trabajar adecuadamente con esta información, fue necesario normalizar estas estructuras, separando los diccionarios en columnas individuales que representaran cada característica del cliente.

Posteriormente se realizaron diversas tareas de limpieza y transformación, entre ellas:

Verificación de valores nulos o faltantes, identificando algunas variables con datos incompletos, principalmente relacionadas con servicios de internet y cargos totales.

Revisión de registros duplicados, utilizando la columna customerID como identificador único de cada cliente.

Estandarización de variables categóricas, convirtiendo valores textuales como Yes y No a valores binarios (1 y 0) para facilitar el análisis y el procesamiento matemático.

Renombrado de columnas para mejorar la claridad de la información, traduciendo algunos nombres técnicos a términos más comprensibles. Por ejemplo:

Charges.Monthly se renombró como Cargos_Mensuales

Charges.Total se renombró como Cargos_Totales

tenure se renombró como Antiguedad_Cliente

Creación de una nueva variable llamada Cuentas_Diarias, calculada a partir de los cargos mensuales divididos entre 30 días. Esta transformación permite estimar el gasto diario de los clientes y analizar el comportamiento de consumo con mayor detalle.

Gracias a estos pasos se obtuvo un conjunto de datos más limpio, consistente y preparado para el análisis exploratorio.

 # Análisis Exploratorio de Datos

Una vez preparados los datos, se realizó un análisis exploratorio con el objetivo de comprender mejor las características de los clientes y su relación con la cancelación del servicio.

Primero se calcularon estadísticas descriptivas como media, mediana, desviación estándar y valores mínimos y máximos para variables numéricas importantes, entre ellas:

- Antigüedad del cliente

- Cargos mensuales

- Cargos totales

- Gasto diario estimado

Estas métricas permitieron obtener una visión general sobre la distribución de los datos y el comportamiento de los clientes.

Posteriormente se analizó la distribución de la variable Churn, utilizando gráficos para visualizar la proporción de clientes que permanecen en el servicio frente a aquellos que han cancelado su suscripción. Este análisis permitió identificar el nivel de evasión dentro del conjunto de datos.

En una etapa posterior se exploró la relación entre la evasión y diversas variables categóricas, tales como:

Género del cliente

Tipo de contrato

Método de pago

Tipo de servicio de internet

Los gráficos permitieron observar patrones interesantes en el comportamiento de los clientes, identificando ciertos perfiles con mayor tendencia a cancelar el servicio.

Finalmente, también se analizaron variables numéricas en relación con el churn, comparando la distribución de variables como la antigüedad del cliente, los cargos mensuales y el gasto total entre clientes que permanecen y aquellos que cancelaron el servicio. Para ello se utilizaron gráficos comparativos que facilitaron la identificación de posibles diferencias entre ambos grupos.

# Conclusiones e Insights

El análisis permitió identificar varios patrones relevantes relacionados con la evasión de clientes.

Uno de los hallazgos más importantes es que los clientes con contratos mensuales presentan una mayor tendencia a cancelar el servicio en comparación con aquellos que tienen contratos de mayor duración, como los contratos anuales o de dos años. Esto sugiere que la estabilidad contractual puede influir significativamente en la permanencia de los clientes.

También se observó que los clientes con menor antigüedad tienen una mayor probabilidad de cancelar el servicio, lo que indica que los primeros meses de relación con la empresa son un periodo crítico para la retención de clientes.

Otro aspecto relevante es que los cargos mensuales más elevados pueden estar asociados con una mayor tasa de cancelación, lo que podría indicar que algunos clientes perciben el servicio como costoso en relación con el valor recibido.

En general, el análisis muestra que factores relacionados con el tipo de contrato, el tiempo de permanencia y el costo del servicio influyen en el comportamiento de cancelación de los clientes.

# Recomendaciones

Con base en los resultados obtenidos, se proponen varias acciones estratégicas que podrían ayudar a reducir la evasión de clientes.

En primer lugar, se recomienda promover contratos de mayor duración, ofreciendo incentivos o beneficios adicionales para los clientes que opten por planes anuales o de dos años. Este tipo de estrategias puede ayudar a aumentar la permanencia de los clientes.

También sería conveniente fortalecer la experiencia de los nuevos clientes, especialmente durante los primeros meses del servicio, implementando programas de acompañamiento, soporte técnico y seguimiento para garantizar una buena experiencia inicial.

Otra recomendación es evaluar la estructura de precios y los planes ofrecidos, asegurando que los cargos mensuales sean percibidos como competitivos y acordes con el valor del servicio.

Finalmente, se podrían desarrollar estrategias de retención basadas en análisis de datos, identificando perfiles de clientes con mayor riesgo de cancelación y aplicando acciones preventivas antes de que abandonen el servicio.

Implementar estas medidas podría contribuir a mejorar la satisfacción del cliente, aumentar la fidelización y reducir la tasa de evasión, generando beneficios tanto para la empresa como para sus usuarios.
