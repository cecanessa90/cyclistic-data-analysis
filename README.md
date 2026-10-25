# Cyclistic | Análisis de datos de bicicletas compartidas

**Proyecto final — Certificado Profesional de Análisis de Datos de Google**

## Descripción del proyecto

Este proyecto consiste en un análisis de los patrones de uso de Cyclistic, una empresa ficticia de bicicletas compartidas ubicada en Chicago.

El objetivo es comprender las diferencias de comportamiento entre los usuarios con membresía anual (`member`) y los usuarios casuales (`casual`), para aportar información que permita desarrollar estrategias de marketing orientadas a convertir usuarios casuales en miembros anuales.

El trabajo recorre las seis etapas del proceso de análisis de datos: **Preguntar, Preparar, Procesar, Analizar, Compartir y Actuar**.

## Pregunta de negocio

**¿En qué se diferencian los patrones de uso de bicicletas entre los miembros anuales y los usuarios casuales?**

Para responderla, se analizaron:

- La cantidad y duración de los viajes.
- Los patrones de uso por día de la semana y horario.
- Las diferencias entre días laborables y fines de semana.
- La evolución mensual y la estacionalidad.
- Las preferencias según el tipo de bicicleta.

## Herramientas utilizadas

| Herramienta | Aplicación |
|---|---|
| Python | Procesamiento y análisis de datos |
| Pandas | Limpieza, transformación y agrupación de datos |
| Google Colab | Desarrollo y ejecución de notebooks |
| Tableau Public | Visualización interactiva y comunicación de resultados |
| ChatGPT | Apoyo al aprendizaje, revisión de código y documentación |
| GitHub | Documentación y publicación del proyecto |

### Uso de inteligencia artificial

Durante el desarrollo del proyecto utilicé ChatGPT como herramienta de apoyo para el aprendizaje, la resolución de dudas técnicas, la revisión de código y la documentación.

El proceso de análisis se desarrolló de manera activa, trabajando sobre la comprensión de los procedimientos, la interpretación de los resultados y la elaboración de conclusiones propias.

La inteligencia artificial se utilizó como herramienta de asistencia, no como sustituto del razonamiento analítico.

## Conjunto de datos

Se utilizaron registros de viajes de bicicletas compartidas correspondientes al período **septiembre de 2025 a agosto de 2026**.

El conjunto de datos original contenía **6.115.982 viajes**.

Durante la preparación se realizaron controles de calidad, identificación de registros duplicados, cálculo de la duración de los viajes y detección de valores extremos.

Entre los procedimientos realizados se destacan:

- Eliminación de 35 registros con identificadores de viaje duplicados.
- Identificación de viajes con duración inferior a 1 minuto o superior a 120 minutos.
- Conservación de los valores extremos mediante una variable de clasificación, permitiendo comparar resultados con y sin estos registros.
- Exclusión de 268 viajes fuera del período definido para el análisis final.

**Conjunto de datos final: 6.115.679 viajes.**

| Tipo de usuario | Cantidad de viajes | Participación |
|---|---:|---:|
| Miembros anuales | 3.955.554 | 64,7 % |
| Usuarios casuales | 2.160.125 | 35,3 % |
| **Total** | **6.115.679** | **100 %** |

Los archivos originales de gran tamaño no se incluyen en este repositorio.

## Metodología

El análisis se desarrolló utilizando Python y Pandas, mediante cuatro notebooks de Jupyter.

### 1. Control y preparación de datos

`controles_prepare.ipynb`

Revisión de la estructura de los datos, controles de calidad, identificación de duplicados y preparación de variables para el análisis.

### 2. Consolidación de datos

`analisis_12_mes.ipynb`

Integración de los archivos mensuales en un único conjunto de datos correspondiente al período estudiado.

### 3. Análisis exploratorio

`fase4_analyze.ipynb`

Estudio de las diferencias entre miembros anuales y usuarios casuales, considerando duración, frecuencia, distribución semanal y horaria, estacionalidad y tipos de bicicleta.

### 4. Preparación de visualizaciones

`fase5_share.ipynb`

Construcción y exportación de tablas resumidas en formato CSV para su posterior visualización en Tableau.

**Nota sobre el entorno:** los notebooks fueron desarrollados en Google Colab utilizando archivos almacenados en Google Drive. Para ejecutarlos en otro entorno es necesario adaptar las rutas de acceso a los datos.

## Principales hallazgos

### 1. Los miembros anuales realizan la mayor cantidad de viajes

Los miembros anuales representan aproximadamente el **64,7 % de los viajes**, mientras que los usuarios casuales realizan el 35,3 % restante.

### 2. Los usuarios casuales realizan viajes más largos

La duración promedio de los viajes presenta diferencias importantes entre ambos grupos.

| Tipo de usuario | Promedio general | Sin valores extremos |
|---|---:|---:|
| Miembros anuales | 12,37 min | 11,63 min |
| Usuarios casuales | 20,66 min | 16,42 min |

Los usuarios casuales realizan viajes de mayor duración promedio, incluso cuando se excluyen los valores extremos.

### 3. Existen diferencias en los patrones semanales y horarios

La comparación de los viajes por día de la semana y hora de inicio permite identificar comportamientos diferenciados entre ambos grupos y explorar su relación con desplazamientos cotidianos y actividades recreativas.

### 4. La demanda presenta variaciones estacionales

La evolución mensual muestra cambios en la cantidad de viajes a lo largo del año, lo que sugiere una influencia de las estaciones sobre los patrones de uso.

### 5. El tipo de bicicleta aporta información adicional

La comparación de los tipos de bicicleta utilizados permite complementar el análisis de los comportamientos y preferencias de cada grupo.

## Limitaciones del análisis y oportunidades de mejora

Una de las principales limitaciones del conjunto de datos es que la información disponible corresponde a los viajes realizados y no a los usuarios individuales.

Si bien esto permite identificar diferencias en los patrones de uso entre miembros anuales y usuarios casuales, no es posible determinar cuántas personas distintas utilizan el servicio ni conocer la frecuencia con la que cada usuario realiza viajes.

Por ejemplo, una mayor cantidad de viajes no necesariamente implica una mayor cantidad de usuarios, ya que una misma persona puede realizar múltiples viajes durante el período estudiado.

**Contar con información a nivel de usuario permitiría profundizar el análisis**, especialmente en aspectos como:

- La cantidad de usuarios únicos de cada categoría.
- La frecuencia de uso individual y la identificación de usuarios casuales recurrentes.
- La evolución de los hábitos de uso de una misma persona.
- La identificación de perfiles con mayor potencial de conversión a una membresía anual.

Esta información permitiría desarrollar recomendaciones comerciales más precisas, orientadas no solamente a los patrones generales de uso, sino también al comportamiento de los distintos perfiles de clientes.

Por lo tanto, considero que **incorporar información anonimizada a nivel de usuario sería un paso importante para futuras investigaciones**, siempre respetando los criterios de privacidad y protección de datos.

## Visualización de resultados y recomendaciones

Los principales hallazgos, sus interpretaciones y las recomendaciones de negocio se presentan en una historia interactiva desarrollada en Tableau Public.

**[Ver el análisis completo de Cyclistic en Tableau](https://public.tableau.com/app/profile/cesar.canessa/viz/Cyclistic-Analisisdeusuarios/Cyclistic-Historia)**

La visualización integra los resultados del análisis y permite comprender las diferencias entre los usuarios casuales y los miembros anuales, vinculándolas con la pregunta de negocio original.

## Conclusión

Este proyecto permitió desarrollar un proceso completo de análisis de datos, desde la preparación y validación de un conjunto de más de seis millones de registros hasta la identificación de patrones, la elaboración de visualizaciones y la comunicación de resultados.

El trabajo pone énfasis en **transformar datos en información útil para la toma de decisiones**, combinando herramientas técnicas, análisis estadístico e interpretación de resultados.

También representó una oportunidad para incorporar la inteligencia artificial como herramienta de apoyo al trabajo analítico, manteniendo el foco en la comprensión de los procesos y el desarrollo de criterios propios.

---

**Autor:** César Canessa

**Proyecto:** Certificado Profesional de Análisis de Datos de Google

**Tecnologías:** Python · Pandas · Google Colab · Tableau Public · ChatGPT
