# Sprint7-final-project
Análisis ConnectaTel -- Como **analista de datos**, se evaluó el **comportamiento de los clientes** de una empresa de telecomunicaciones en Latinoamérica, ConnectaTel.

Análisis de Comportamiento de Clientes - ConnectaTel (Latam) 📊📞
📋 Descripción del Proyecto
Este proyecto analiza el comportamiento de los usuarios de la empresa de telecomunicaciones ConnectaTel en Latinoamérica durante el periodo hasta 2024. El objetivo principal es identificar patrones de consumo, detectar anomalías en los datos y segmentar a los usuarios según su uso de servicios de voz y texto.

🛠️ Tecnologías Utilizadas
Python 3.x

Jupyter Notebook

Pandas: Para la manipulación y limpieza de datos.

Matplotlib & Seaborn: Para la visualización de datos y análisis estadístico.

📂 Estructura de los Datasets
El análisis se basa en tres fuentes de datos principales:

plans.csv: Detalles de las tarifas (Básico y Premium), minutos/mensajes incluidos y costos excedentes.

users_latam.csv: Información demográfica de los usuarios (edad, ciudad, fecha de registro y plan).

usage.csv: Registro detallado de cada evento de consumo (llamadas en minutos y mensajes de texto).

🛠️ Proceso de Limpieza y Preparación (Data Wrangling)
El dataset original contenía inconsistencias que fueron corregidas para asegurar la fiabilidad del análisis:

Tratamiento de Valores Nulos:

Columna city: Los valores faltantes se marcaron como "Unknown" para no perder registros valiosos durante la segmentación geográfica.

Columna churn_date: Se determinó que los nulos representan a usuarios activos. Se mantuvieron así para análisis de retención.

Corrección de Valores Centinela (Sentinels):

Se identificaron registros con edad -999. Estos fueron imputados utilizando la mediana de la edad (48 años) para eliminar el sesgo negativo en las estadísticas descriptivas.

Estandarización de Categorías:

Se eliminaron caracteres especiales como ? en la columna de ciudades, reemplazándolos por etiquetas legibles.

Se verificó la consistencia en los nombres de los planes (Basico vs Premium).

Optimización de Tipos de Datos:

Las columnas de fechas (registros y bajas) fueron convertidas al formato datetime64 para permitir análisis de series de tiempo.

🔍 Hallazgos Clave (EDA)
Durante la fase de Exploración de Datos (EDA), se identificaron los siguientes puntos críticos:

Datos Corruptos: Se detectaron valores centinela (−999) en la columna de edad y caracteres especiales (?) en la ubicación geográfica.

Distribución de Planes: El plan Básico domina el mercado, especialmente en ciudades como Bogotá y CDMX.

Patrones de Uso: Existe una ligera preferencia por el uso de mensajes de texto (55%) sobre las llamadas de voz (45%).

Outliers: Se detectaron consumos atípicos en la duración de llamadas y longitud de mensajes que requieren un tratamiento especial para no sesgar el análisis.

TIPS
🚀 Ejecución en Google Colab
Puedes ejecutar este análisis de forma gratuita en la nube siguiendo estos pasos:

1. Abrir el Notebook
Opción A (Directa): Ve a Google Colab.

Opción B (Desde GitHub): En Colab, selecciona la pestaña GitHub, pega la URL del repositorio y selecciona el archivo .ipynb.

2. Cargar los Datasets
Para que el código funcione, debes subir los archivos .csv al entorno de Colab:

En la barra lateral izquierda, haz clic en el icono de la Carpeta (Archivos).

Arrastra y suelta los archivos plans.csv, users_latam.csv y usage.csv dentro del panel.

⚠️ Nota: Si cierras la sesión de Colab, los archivos se borrarán del entorno temporal. Deberás volver a subirlos la próxima vez.

3. Ejecutar las Celdas
Puedes ejecutar cada celda de código presionando Shift + Enter.

Para ejecutar todo el análisis de una vez, ve al menú superior: Entorno de ejecución > Ejecutar todas.

📂 Estructura de Archivos Necesaria
Para evitar errores de "File Not Found", asegúrate de que tus archivos estén en la ruta raíz del panel de Colab:

Plaintext
/content/
 ├── plans.csv
 ├── users_latam.csv
 └── usage.csv
