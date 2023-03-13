<p align=center><img src=https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png><p>

# <h1 align=center> **PROYECTO INDIVIDUAL Nº1** </h1>

# <h1 align=center>**`Machine Learning Operations (MLOps)`**</h1>

<p align="center">
<img src="https://user-images.githubusercontent.com/67664604/217914153-1eb00e25-ac08-4dfa-aaf8-53c09038f082.png"  height=300>
</p>

¡Bienvenidos al primer proyecto individual de la etapa de labs! En esta ocasión, deberán hacer un trabajo situándose en el rol de un ***MLOps Engineer***.  

<hr>  

## **Descripción del problema (Contexto y rol a desarrollar)**

## Contexto

Tienes tu modelo de recomendación entrenado dando unas buenas métricas :smirk:, y ahora, cómo lo llevas al mundo real? :eyes:

El ciclo de vida de un proyecto de Machine Learning debe contemplar desde el tratamiento y recolección de los datos (Data Engineer stuff) hasta el entrenamiento y mantenimiento del modelo de ML según llegan nuevos datos.


## Rol a desarrollar

Empezaste a trabajar como **`Data Scientist`** en una start-up que provee servicios de agregación de plataformas de streaming. El mundo es bello y vas a crear tu primer modelo de ML que soluciona un problema de negocio: un sistema de recomendación que aún no ha sido puesto en marcha! 

Vas a sus datos y te das cuenta que la madurez de los mismos es poca (ok, es nula :sob:): Datos sin transformar, no hay procesos automatizados para la actualización de nuevas películas o series, entre otras cosas….  haciendo tu trabajo imposible :weary:. 

Debes empezar desde 0, haciendo un trabajo rápido de **`Data Engineer`** y tener un **`MVP`** (_Minimum Viable Product_) para la próxima semana! Tu cabeza va a explotar 🤯, pero al menos sabes cual es, conceptualmente, el camino que debes de seguir :exclamation:. Así que te espantas los miedos y te pones manos a la obra :muscle:

<p align="center">
<img src="https://github.com/soyHenry/DS_LABS/blob/main/Proyectos/Proyectos%20Individuales/PI01/Data07_MLops_API/src/DiagramaConceptualDelFlujoDeProcesos.png"  height=500>
</p>

<sub> Nota que aqui se reflejan procesos no herramientas tecnologicas. Has el ejercicio de entender cual herramienta del stack corresponde a cual parte del proceso<sub/>

## **Propuesta de trabajo (requerimientos de aprobación)**

**`Transformaciones`**:  Para este MVP no necesitas perfección, ¡necesitas rapidez! ⏩ Vas a hacer estas, ***y solo estas***, transformaciones a los datos:


+ Generar campo **`id`**: Cada id se compondrá de la primera letra del nombre de la plataforma, seguido del show_id ya presente en los datasets (ejemplo para títulos de Amazon = **`as123`**)

+ Los valores nulos del campo rating deberán reemplazarse por el string “**`G`**” (corresponde al maturity rating: “general for all audiences”

+ De haber fechas, deberán tener el formato **`AAAA-mm-dd`**

+ Los campos de texto deberán estar en **minúsculas**, sin excepciones

+ El campo ***duration*** debe convertirse en dos campos: **`duration_int`** y **`duration_type`**. El primero será un integer y el segundo un string indicando la unidad de medición de duración: min (minutos) o season (temporadas)

<br/>

**`Desarrollo API`**:   Propones disponibilizar los datos de la empresa usando el framework ***FastAPI***. Las consultas que propones son las siguientes:

+ Película con mayor duración con filtros opcionales de AÑO, PLATAFORMA Y TIPO DE DURACIÓN. (la función debe llamarse get_max_duration(year, platform, duration_type))

+ Cantidad de películas por plataforma con un puntaje mayor a XX en determinado año (la función debe llamarse get_score_count(platform, scored, year))

+ Cantidad de películas por plataforma con filtro de PLATAFORMA. (La función debe llamarse get_count_platform(platform))

+ Actor que más se repite según plataforma y año. (La función debe llamarse get_actor(platform, year))


<br/>


**`Deployment`**: Conoces sobre [Render](https://render.com/docs/free#free-web-services) y tienes un [tutorial de Render](https://github.com/HX-FNegrete/render-fastapi-tutorial) que te hace la vida mas facil :smile: . Tambien podrias usar [Railway](https://railway.app/), pero ten en cuenta que con este si necesitas dockerizacion.

<br/>

**`Análisis exploratorio de los datos`**: _(Exploratory Data Analysis-EDA)_

Ya los datos están limpios, ahora es tiempo de investigar las relaciones que hay entre las variables de los datasets, ver si hay outliers o anomalías (que no tienen que ser errores necesariamente :eyes: ), y ver si hay algún patrón interesante que valga la pena explorar en un análisis posterior.  Sabes que puedes apoyarte en librerías como _pandas profiling, sweetviz, autoviz_, entre otros y sacar de allí tus conclusiones 😉

**`Sistema de recomendación`**: 

Una vez que toda la data es consumible por la API ya lista para consumir para los departamentos de Analytics y de Machine Learning, y nuestro EDA bien realizado entendiendo bien los datos a los que tenemos acceso, es hora de entrenar nuestro modelo de machine learning para armar un sistema de recomendación de películas para usuarios, donde dado un id de usuario y una película, nos diga si la recomienda o no para dicho usuario. De ser posible, este sistema de recomendación debe ser deployado para tener una interfaz gráfica amigable para ser utilizada, utilizando Gradio para su deployment o bien con alguna solución como Streamlit o algo similar en local (tener el deployment del sistema de recomendación o una interfaz gráfica es un plus al proyecto).

<br/>

**`Video`**: Necesitas que al equipo le quede claro que tus herramientas funcionan realmente! Haces un video mostrando el resultado de las consultas propuestas y de tu modelo de ML entrenado!

<sub> **Spoiler**: El video NO DEBE durar mas de ***7 minutos*** y DEBE mostrar las consultas requeridas en funcionamiento desde la API** y una breve explicacion del modelo entrenado para el sistema de recomendacion. <sub/>

<br/>

## **Criterios de evaluación**

**`Código`**: Prolijidad de código, uso de clases y/o funciones, en caso de ser necesario, código comentado. 

**`Repositorio`**: Nombres de archivo adecuados, uso de carpetas para ordenar los archivos, README.md presentando el proyecto y el trabajo realizado

**`Cumplimiento`** de los requerimientos de aprobación indicados en el apartado `Propuesta de trabajo`

NOTA: Recuerde entregar el link de acceso al video. Puede alojarse en YouTube, Drive o cualquier plataforma de almacenamiento. **Verificar que sea de acceso público**.

<br/>
Aqui te sintetizamos que es lo que consideramos un MVP aprobatorio, y la diferencia con un producto completo.
https://github.com/HX-PRomero/PI_ML_OPS/blob/main/src/MVP_MLops.png

<p align="center">
<img src="https://github.com/HX-PRomero/PI_ML_OPS/blob/main/src/MVP_MLops.png"  height=250>
</p>


## **Fuente de datos**

+ [Dataset](https://drive.google.com/drive/folders/1b49OVFJpjPPA1noRBBi1hSmMThXmNzxn): La carpeta 'ratings' tiene varios archivos con las reseñas de los usuarios, la carpeta raíz tiene un dataset por proveedor de servicios de streaming.
<br/>

## **Material de apoyo**

En este mismo repositorio podras encontrar algunos [links de ayuda](https://github.com/soyHenry/DS_LABS/blob/main/Proyectos/Proyectos%20Individuales/PI01/Data08_MLops/Material%20de%20apoyo.md). Recuerda que no son los unicos recursos que puedes utilizar!


  
<br/>

## **Deadlines importantes**

+ Apertura de formularios de entrega de proyectos: **Lunes 20, 10:00 hs gmt -3**

+ Cierre de formularios de entrega de proyectos: **Martes 21, 16:00hs gmt-3**
  
+ Demo: **Martes 21, 16:00hs gmt-3*** 
