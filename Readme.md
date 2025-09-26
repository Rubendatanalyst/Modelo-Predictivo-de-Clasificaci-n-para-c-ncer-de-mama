# Predicción de Cancer de mama

**_Cáncer de mama_**

El cáncer de mama es el tipo de cáncer más frecuente y la causa más común de muerte por cáncer en mujeres a nivel mundial. El cáncer de mama causa más años de vida perdidos por discapacidad perdidos en mujeres que cualquier otro cáncer. La carga de enfermedad que representa el cáncer de mama es desproporcionadamente mayor en los países en vías de desarrollo, donde la mayoría de las muertes por cáncer de mama ocurren prematuramente, en mujeres menores de 70 años.
El pronóstico después de un diagnóstico de cáncer de mama ha mejorado dramáticamente en los países de altos ingresos, los cuales han tenido una disminución del 40% en mortalidad por cáncer de mama (estandarizada por edad) entre 1980 y 2020, tras la introducción de programas de detección temprana y protocolos de tratamiento estandarizados. La detección precoz y el acceso a tratamiento efectivo siguen siendo un reto para países con recursos limitados, a pesar de que existen intervenciones probadas y rentables. Se pueden lograr mejoras sustanciales en el control global del cáncer de mama mediante la implementación de lo que ya sabemos que funciona.

**_Datos clave_**

•	El cáncer de mama es el cáncer más común y la causa más común de muerte por cáncer en las mujeres en las Américas.
•	Las características que se asocian con un mayor riesgo de desarrollar cáncer de mama incluyen la obesidad, consumo de alcohol, antecedentes familiares de cáncer de mama, exposición a radiación, antecedentes reproductivos y hormonales y consumo de tabaco. Alrededor de la mitad de los casos se desarrollan en mujeres sin factores de riesgo identificados además de ser mujeres con 40 años de edad o más.
•	El cáncer de mama surge en las células de revestimiento de los conductos (85%) o lóbulos (15%) del tejido glandular de la mama.
•	Cuando el cáncer se limita al conducto o lóbulo donde comenzó, no causa síntomas, pero puede eventualmente progresar e invadir el tejido circundante y, finalmente, los ganglios linfáticos locales y otros órganos.
•	La carga de enfermedad por cáncer de mama se puede reducir mediante la identificación y el tratamiento temprano de los cánceres, antes de que den síntomas. En contextos con suficientes recursos, se recomienda el tamizaje organizado con mamografía cada dos años para las mujeres de 50 a 69 años. En entornos de recursos limitados, donde los programas de detección de mamografías pueden no ser factibles, el examen clínico de mama parece ser .
•	El cáncer de mama se presenta con mayor frecuencia como una masa indolora en la mama. Es importante que las mujeres que encuentren una masa consulten a un profesional de salud lo antes posible, incluso si no causa dolor.
•	Las masas en las mamas pueden desarrollarse por razones distintas al cáncer (hasta el 90%). El cáncer de mama puede presentarse de muchas maneras, por lo que es importante un examen médico completo. Otros síntomas del cáncer de mama incluyen engrosamiento de la mama, alteración en el tamaño, la forma o la apariencia de la mama, alteraciones de la piel como enrojecimiento, picaduras o hoyuelos, cambio en la apariencia del pezón o la piel alrededor (areola), y/o secreción anormal del pezón. Los cánceres de mama avanzados pueden erosionarse a través de la piel y propagarse a otras partes del cuerpo, desencadenando síntomas adicionales.
•	El tratamiento del cáncer de mama puede ser eficaz, especialmente cuando se detecta a tiempo. Por lo general, implica cirugía con o sin radiación y medicamentos. La efectividad del tratamiento depende de someterse al curso completo del tratamiento.
•	Los cuidados paliativos y de apoyo ayudan a mejorar la calidad de vida de las pacientes y sus familias y también pueden influir positivamente en el curso de la enfermedad, con el objetivo de satisfacer las necesidades de atención de apoyo, psicosociales y espirituales de las mujeres con cáncer de mama.

**_Contexto_**

El objetivo pricipal es desarrollar modelos predictivos para el diagnóstico de cáncer de mama. El dataset (disponible a través de Kaggle), está diseñado para tareas de clasificación binaria para predecir si un tumor de mama es benigno o maligno. Proporciona una rica colección de características derivadas de imágenes digitalizadas de aspirados con aguja fina (FNA) de masas mamarias, lo que lo convierte en una herramienta esencial para avanzar en el análisis de la atención médica y la patología computacional.

El análisis se realiza bajo la siguiente estructura:

•   Identificación y separación de los grupos.
•   Aplicación de los modelos de clasificación para cada grupo: Regresión Linear, Arbol de Decisión, Random Forrest, Gradient Boosting.
•   Cálculos de las metricas: accuracy, presicion, recall, f1 para cada modelo.
•   Gráficas de los resultados.    

**_Descripción de los datos_**

***Columnas Clave:***

•	ID: Un identificador único para cada muestra (p. ej., 842302).
•	Diagnosis: La variable objetivo, etiquetada como:
    o	M (Maligno): Indica un tumor canceroso.
    o	B (Benigno): Indica un tumor no canceroso.
•	Características (30 columnas): Mediciones numéricas de núcleos celulares, como el radio, la textura, el perímetro y el área, derivadas del análisis de imágenes.

***Categorías de Características***

Las 30 características se agrupan en tres categorías principales basadas en las características de los núcleos celulares:
•	Media (Mean): Valores promedio de las mediciones (p. ej., radio medio, textura media).
•	Error Estándar (SE): Variabilidad de las mediciones (p. ej., error estándar del radio, error estándar del área).
•	Peor (Worst): Los valores más grandes (peores) de las mediciones (p. ej., peor radio, peor suavidad).

Cada categoría incluye 10 mediciones específicas:

1.	Radio (media de las distancias desde el centro a los puntos del perímetro)
2.	Textura (desviación estándar de los valores en escala de grises)
3.	Perímetro
4.	Área
5.	Suavidad (variación local en las longitudes del radio)
6.	Compacidad (perímetro² / área - 1.0)
7.	Concavidad (gravedad de las porciones cóncavas del contorno)
8.	Puntos cóncavos (número de porciones cóncavas del contorno)
9.	Simetría
10.	Dimensión fractal ("aproximación a la línea de costa" - 1)


**Conclusiones**

Según los resultados obtenidos podriamos considerar lo siguiente para cada grupo y el mejor modelo que aplica:

Peor (Worst)	Regresión Logística	1.00
Media (Mean)	Gradient Boosting	0.99
Error Estándar (SE)	Gradient Boosting	0.97

A pesar de los resultados anteriores, para este caso en específico es mejor considerar las métricas de Sensibilidad (Recall) y Puntaje F1 (F1-Score) para evaluar el modelo de clasificación como el de predicción de cáncer de mama por una razón fundamental: manejan de manera efectiva el problema del desbalance de clases y priorizan la minimización del error con la consecuencia más grave.

Recall:

Peor (Worst)            Logistic Regression y Decision Tree 	0.979 (ambos)
Media (Mean)	        Gradient Boosting	                    0.957
Error Estándar (SE)		Random Forest y Gradient Boosting       0.915

F1 Score:

Peor (Worst)            Logistic Regression     0.979 
Media (Mean)            Gradient Boosting	    0.947
Error Estándar (SE)     Gradient Boosting	    0.896


Al considerar estas métricas podemor abordar el problema central de la medicina diagnóstica: el alto costo de un error y el desbalance de clases. 

La métrica Recall es la métrica más crítica en el diagnóstico médico porque mide la capacidad del modelo para detectar a todos los casos positivos reales (pacientes que tienen cáncer). Se centra en minimizar los Falsos Negativos (FN), que son los casos de cáncer que el modelo pasa por alto. En el diagnóstico de cáncer, un Falso Negativo es el error más grave. Significa que una paciente con cáncer es diagnosticada como sana y no recibe el tratamiento vital a tiempo. Una alta Sensibilidad es la garantía de que el modelo está optimizado para no perder ningún caso de cáncer, que es el objetivo primordial de cualquier herramienta de detección.

La métrica F1 score es la media armónica de la Sensibilidad (Recall) y la Precisión (Precision). Esto lo convierte en la métrica más confiable para un rendimiento equilibrado. Un modelo puede tener una Sensibilidad perfecta (1.0) si predice que todos tienen cáncer. Pero eso generaría muchísimas Falsas Alarmas (Falsos Positivos). La Precisión mide la proporción de predicciones positivas que fueron realmente correctas, penalizando estas alarmas innecesarias. Esta métrica obliga al modelo a ser bueno en ambas cosas: detectar la mayoría de los casos y no generar una cantidad abrumadora de falsas alarmas. Al considerar esta métrica aseguramos que el modelo es robusto, ya que un buen puntaje indica un balance exitoso entre la capacidad de detección y la exactitud de las predicciones positivas.