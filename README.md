#Proyecto 2: modelos de Regresión con Python

*Asignatura:* Programación Python Avanzada  
*Institución:* Universidad Provincial del Sudoeste (UPSO)  
*Integrantes:* Carluccio Ros Bruno & González Agustín

# 1. Cual fue el desempeño del modelo?

 Al analizar los datos como el r2, MAE, RMSE se explican varios de los comportamientos del modelo.
Para empezar el MAE o error absoluto promedio en test es 1.059.490, es decir que el modelo se equivoca por un millon y poco mas, para saber si ese valor es mucho o poco usamos el MAE del baseline que nos da 1.405.860, es decir redujo el error en un 24%. 
 Al tener un MAE menor que el baseline podemos concluir que las variables utilizadas aportan a la prediccion.
Pero el dato mas importante es R2 (coeficiente de determinacion); en nuestro caso dio un resultado de 0.299, osea que la proporcion de la variacion del target que explica nuestro modelo es de un 30%, por lo que nos queda un 70% sin explicar.
Podemos concluir que el desempeño del modelo fue regular, y es logico ya que hay muchas variables no contempladas en el dataframe que pesan mucho a la hora de determinar el patrimonio de una persona. 

# 2. Qué variable fue la más influyente según los coeficientes del modelo?

 Segun la tabla de coeficientes, la variable mas influyente es annual_savings (ahorros anuales) con un coeficiente de 32,33. Este valor indica cuanto aumenta el patrimonio predicho por cada dolar ahorrado, (multiplica esos dolares por 32,33).
 Al estandarizarlo multiplicandolos por el desvio de cada variable obtenemos el dato clave; *1322240.08* y el mas grande de todos indicando que es la variable que mas cambia la prediccion del modelo.


# 3. ¿Las features extraídas del dataset fueron buenas predictoras? ¿O sugieren otras?

Respuesta y justificación basada en el grafico 1 :
*Predictores moderados o buenos: Las variables financieras directas fueron las que mejor funcionaron. **annual_savings* (con una correlación de $0.54$ con el patrimonio) y *total_annual_income* ($0.47$) demostraron ser las mejores predictoras, ya que guardan una relación lógica y directa con la acumulación de riqueza *net_worth*, por eso tiene el valor mas cercano a 1. Tambien el r2 global al ser de un valor bajo (0.299) concluimos que el conjunto en total de features predice poco.

*Predictores débiles: Variables como **age* ($0.23$) y *years_of_experience* ($0.22$) tienen una correlación débil, mientras que *education_years* ($0.18$) aporta muy poco y *weekly_work_hours* ($0.01$) muestra una correlación prácticamente nula con el patrimonio. En conclusion no son buenas predictoras pero las utilizamos a modo de demostrar que habitos o datos hacen a la persona mas o menos rica por ejemplo las horas trabajadas no influyen realmente en el patrimonio.

Sugeririamos variables que realmente determinen su patrimonio en la vida real como inversiones y deudas.

# 4.Comparativa de resultados de evaluación del modelo con los datos de Entrenamiento y de Test.

Comparativa numérica: El modelo obtuvo un $R^2$ de $0.351$ en entrenamiento y de $0.299$ en testeo.

Justificación con el gráfico *Real vs Predicho* (grafico punto 7 izquierda):
Se ve que los puntos se concentran densamente en la zona inferior izquierda (patrimonios más comunes) y se alejan fuertemente de la línea roja punteada de "predicción perfecta" a medida que aumentan los valores. El modelo subestima severamente a las personas con patrimonios muy altos (por ejemplo, patrimonios reales superiores a 10 o 20 millones son predichos por debajo de los 5 millones).

Justificación con el gráfico *Residuos* (grafico punto 7 derecha):
Los errores (residuos) no se distribuyen como un ruido aleatorio y homogéneo alrededor del cero. Forman una estructura de embudo, lo que confirma que a mayor valor predicho, mayor es el error y la dispersión, demostrando que la relación lineal no logra explicar por completo la variabilidad de los datos extremos.