# Online Retail II - ABC Product Analysis
Este repositorio documenta el proceso de limpieza, transformación y análisis exploratorio del conjunto de datos "online_retail_II", utilizando en su mayoría Power Query de Excel.
Este proyecto sigue el marco de trabajo del Certificado Profesional de Análisis de Datos de Google, delimitado por los pasos correspondientes a cada etapa del proceso: **Ask, Prepare, Process, Analyze, Share and Act.**
## Ask (Preguntar)
El dataset original cuenta con una gran cantidad de transacciones de una tienda en línea basada en el Reino Unido en el transcurso de 2 años. Sin embargo, los datos "crudos" presentan inconsistencias que impiden un análisis confiable, se incluye una mezcla de datos de ventas reales con errores, pruebas y devoluciones.
El objetivo del proyecto es limpiar el contenido del dataset, asegurando la integridad de los datos y realizar un análisis "ABC" de los productos comercializados, presentando visualizaciones y proponiendo alternativas de mejora de eficiencia en manejo de inventarios.
## Prepare (Preparar)
- Fuente de datos "online_retail_II" extraído de *Kaggle*.
- Formato original *.csv*
- Volumen de 1,000,000 de filas aproximadamente.
- Dataset conectado directamente a *Power Query* para limpieza.
## Process (Procesar)
La parte fundamental del proyecto, se comenzó por verificar los correctos tipos de datos en cada columna, verificando que fechas, números y textos coincidieran. Se agrega la columna de *TotalSale* calculando el valor completo de la venta por cada invoice. Al ordenar los datos por mayor venta de manera descendente, me comienzo a percatar de las inconsistencias existentes en la información; existen códigos con dígitos únicos y descripciones no correspondentes al igual que cantidades nulas. Se filtran y remueven cantidades nulas y se procede a agregar una columna nueva que arroje el largo de cada código, analizando que deben ser mayor a 4 dígitos, se procede a filtrar. Para mi sorpresa, esto no fue suficiente. Existían códigos correctos con cantidades correctas que correspondían a descripciones erróneas, no a invoices; se procede a crear una nueva columna extrayendo únicamente el primer dígito (todos los códigos correctos comenzaban con números, nunca con letras), se procede a filtrar. Listo, hemos limpiado correctamente el datastet; se procede a crear una copia agrupando la misma por *SKU* y arrojando valores de *Quantity* y *TotalSale*. Finalmente se unen ambas versiones en un modelo de datos en Excel para facilitar alguna unión de tabla dinámica.
<img width="1675" height="811" alt="image" src="https://github.com/user-attachments/assets/7197745a-9ea9-45b5-832e-49056728576d" />
 ## Analyze (Analizar)
 Para el proceso de análisis se crearon 2 columnas adicionales, una proyectando el porcentaje de participación por SKU en las ventas totales y la otra una suma del porcentaje acumulado. Finalmente se creó una última columna de clasificación "ABC" según el porcentaje acumulado, siendo menor a 0.80 un producto A, 0.95 B y restantes C. Como era de esperarse la distribución fue la correcta, obteniendo un 79.983% de ingresos totales por parte de productos tipo A, 15.011% de productos tipo B y finalmente 5.006% del tipo C.
 <img width="1241" height="346" alt="image" src="https://github.com/user-attachments/assets/715b9179-a2bf-41ec-8c88-83ea8bcc69ea" />
Finalmente, se generó un dashboard agregando datos más relevantes, KPIs, gráficas y básicamente uniendo todos los conocimientos adquiridos del dataset de manera visual y accesible:
<img width="1116" height="803" alt="image" src="https://github.com/user-attachments/assets/4d6cce7c-5585-4531-82cd-9d8d721eb6ce" />
## Act (Actuar)
Al analizar el dataset *online_retail_II* y generar una clasificación ABC para los múltiples productos comercializados, podemos concluir que existe una gran cantidad de productos de tipo C (alrededor del 50%) que están generando altos costos de almacenamiento e inventario cuando únicamente se encuentran generando el 5% de los ingresos totales, se debe realizar un análisis posterior para determinar si vale la pena seguirlos manteniendo o enfocar esos recursos en mejorar las condiciones de los productos tipo A (alrededor de un 20%) que se encuentran generando el 80% de los ingresos totales.
De igual manera, la mayor concentración de las ventas se encuentran en el Reino Unido, seguido por Irlanda con un muy gran márgen, los servicios deben concentrarse de manera especial en esa sección europea ya que es la que mayor consume. Se vio un incremento muy grande de ventas del año 2009 al 2010, subiendo en unos impactantes 8 millones y reduciendo brevemente el siguiente año.
## Contacto


