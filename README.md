
## Proyecto individual 2 de Julieta Ciare. 

# Introducción.

 Tengo que clasificar por el precio de las propiedades (cara o barata) de una inmobiliaria. Para luego predecir la categorización de baratas o caras con un modelo de Machine Learning. A continuación le estaré mostrando mi procedimiento.

# Paso 1
Visualizo el dataframe de train(properties_colombia_train.csv). Luego hago una función para agregar una columna. Aplicó la función y creo una nueva columna Target. 

# Paso 2
Visualizo lo valores faltantes. Elimino las columnas l4,l5,l6 porque contiene un 70.04 a 96.52% de valores faltantes. Las variables numérica en null le agrego el promedio de cada una de su columna (exepto Target). En la categóricas le pongo NA.

# Paso 3
A no tener nulos en la columna de  precios vuelvo a escribir la función de antes para que la columna Target no tenga valores nulos.

# Paso 4
La variable categórica (property-type) con OneHotEncoder la convierto en numérica. Al pasar a numérica tengo un nuevo dataframe que luego lo conecto con mi dataframe original. ¿Porque elijo Property-type y no otra? Me pareció más relevante porque una casa no va a valer igual que un departamento por eso elegí esa. De todas la columnas del nuevo dataframe me quedo con las columnas Departamento e Casa porque tiene mayor correlación que la otras.

# Paso 5
Descartar y elegir columnas de dataframe principal e unirlas con el nuevo. Solo elijo las columnas que tiene mayor correlación para mí opinión. Luego verifico su correlación con el gráfico Heatmap. Después de varios intentos me quedo con 5 columnas y le conecto con dos columnas más  en total son 7. 

# Paso 7
Asignado variables Y solo para la columna Target y X para la demás.

# Paso 8
Importo Sklearn para decidir el modelo que voy a usar. Pero primero con train_test_split separó los datos de train y de test para luego utilizarlo. Con Pipeline hago el escalado de datos (Standard Scaler) y elección de modelo. Hago tres Pipeline para luego evaluar el modelo que tenga mejor accuracy. En mi caso el mejor accuracy lo tiene el árbol de decisión lo guardo en .pkl. Después llamo el archivo lo entreno e predice los datos de train.

# Paso 9
Utilizo el properties_columbia_test.csv para predecir. Pero primero lo mismo que hago con train convertimos la variable categórica a numérica para unirlo con la demás  columnas que habíamos decidido en el train. A los nulos le agregamos el promedio de cada una de la columnas. Finalmente predecimos el modelo y a la predicción lo convertimos en julieta77.csv.

