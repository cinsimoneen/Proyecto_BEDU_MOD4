
# Predicción de Enfermedad Cardiaca Como Medida de Prevención.

#### Proyecto del Modulo 4 (Machine Learning) del Diplomado de Ciencias de Datos 2024.
#### Autor: Cinthya Simoneen
#### Fecha: Octubre-2024

# Objetivo: 
La enfermedad cardiaca cobra la vida de más personas cada día. Tan solo en México en 2023, las enfermedades del corazón fueron la principal causa de defunción, con 97,187 casos, lo que representa el 25% de las muertes registradas. A nivel mundial, las enfermedades cardiovasculares (ECV) son la principal causa de muerte. Se estima que 17,9 millones de personas fallecieron por ECV, lo que representa el 32% de todas las muertes a nivel global.

Basándonos en indicadores como glucosa en sangre, medición de la presión arterial y otros más, se realiza una predicción de riesgo que nos indica si un paciente está en riesgo de tener enfermedad cardiaca y de ser así derivarlo a un tratamiento preventivo. 

# Información del Dataset
El dataset con los datos necesarios para el proyecto se descarga de Keaggle, el dataset está conformado por:
 <center><img width=300 heigth=400 src="img/columnas.jpg" alt="Información del Dataset" /></center>

<br><br><br>

En donde las columnas contienen la siguiente información:

Indicadores de la columnas
<center><img src="img/ds_info.jpg" alt="Información del Dataset" /></center>


Ejemplo de los datos:

<center><img src="img/df.jpg" alt="Información del Dataset" /></center>

<div style="page-break-after: always"></div>

# Información de los Datos
<br><br>
### Información estadística del Dataset
<center><img src="img/df_estadistica_info.jpg" alt="Información Estadística" /></center>

Edad: Media entre 29 y 77 años<br>
Género de los pacientes:1 = hombre; 0 = mujer<br>
Tipo de dolor de Pecho: 0 = Angina Tipica, 1 = Angina Atipica, 2 = Sin dolor , 3 = Asintomático<br>
Presión Arterial: Media entre 94 y 200 mm Hg.<br>
Colesterol: Media entre 126 y 564 mg/dl.<br>
Glucosa en sangre: > 120 mg/dl 1 = True, 0 = False.<br>
Máxima Frecuencia Cardiaca Durante Ejercicio: Media entre 71 y 202 latidos por minuto<br>
Angina inducida por ejercicio: 1 = si, 0 = no.<br>
Segmento ST deprimido al hacer ejercicio: Media entre 0 y 6.2.<br>
Tipo de Thalassemia: 1 = normal, 2 = tratamiento, 3 = reversible).<br>

<div style="page-break-after: always"></div>

### Gráficas de los datos
<center><img src="img/graficas_indicadores.png" alt="Gráficas_Indicadores" /></center>

<div style="page-break-after: always"></div>

###  Distribución de Enfermedad Cardiaca de acuerdo a Indicadores
<center><img  src="img/ec_vs_indicador.png" alt="Gráficas_Indicadores" /></center>
<center><img  src="img/ec_vs_indicador2.png" alt="Gráficas_Indicadores" /></center>

## Resultado de la revisión del dataset y de los datos
1.) Se cuenta con un total de 1025 registros<br> 
2.) El dataset no contiene registros en NaN<br>
3.) Podría pensarse que entre mas edad se tiene mayor es el riesgo de padecer Enfermedad Cardiaca pero no es así.<br>
4.) Los pacientes con mayor frecuencia cardiaca tienen mayor riesgo de infarto<br>
5.) Los pacientes que no presentan dolor (angina) tienen mayores posibilidades de infartarse<br>
6.) Las mujeres tienen más probabilidad de infarto<br>
7.) Niveles altos de colesterol aumentan el riesgo de infarto<br>
8.) Los pacientes con Thalassemia tienen un riesgo muy alto de infarto<br>

<div style="page-break-after: always"></div>

# Correlación
<center><img src="img/correlacion.png" alt="Correlación" /></center>
De la gráfica de correlación (mapa de calor) se deduce que hay correlación entre el dolor de pecho (angina), la frecuencia cardiaca elevada y la elevación del segmento ST al ejercitarse (Isquemia). Tener estos tres factores aumentan el riesgo de tener un ataque cardiaco.

<div style="page-break-after: always"></div>

# KMEANS
<br>
SCORE=0.8349990481629546
<br>
Utilizando KMEANS se revisa la segmentación de los pacientes por su edad y frecuencia cardiaca en reposo.
<center><img src="img/kmeans.png" alt="KMeans" /></center>
En la segmentación se puede observar que el grupo de pacientes que presentan mayor frecuencia cardiaca en reposo y con esto mayor riesgo de infarto se encuentra entre 35 y 52  años aproximadamente .
<div style="page-break-after: always"></div>

## Árboles Decisión
<br>
SCORE=0.9164683222585133
<br>
<center><img src="img/arbol.png" alt="arbol_decision" /></center>

El modelo ha identificado el inicio de la clasificación con el indicador angina(dolor de pecho)

<div style="page-break-after: always"></div>

# Regresión Logística
<br>
SCORE =0.8512195121951219
<br>
Con datos de prueba se corre el modelo para predecir el riesgo de infarto cardiaco o enfermedad cardiaca los resultados son:
<center><img src="img/df_realvspredicho.jpg" alt="riesgo real vs predicho" /></center>
<center><img src="img/riesgo_real_predicho.png" alt="riesgo real vs predicho" /></center>

<div style="page-break-after: always"></div>

## Conclusión
Con los modelos podemos predecir a que indicadores se les debe prestar mayor atención para prevención de la enfermedad cardiaca o prevenir un infarto cardiaco por ejemplo glucosa en sangre o colesterol.El análisis de está información sirve para seleccionar pacientes que al tener un riesgo de infarto cardiaco puedan seer turnados al Área de Prevención de los Sistemas de Salud.

