# **RecSys**

RecSys está compuesto por un Notebook de Jupyter donde se detallan los pasos a seguir para la realización de un sistema de recomendación basado en contenido de películas. Para ésto se ha empleado el dataset de MovieLends ligeramente modificado (adición de los argumentos de cada película). Basandose en el contenido de los argumentos y los géneros de cada película se han realizado los siguientes sistemas de recomendación.

### **Sist. Recomendación No-Personalizado**

Para el primer sistema se ha usado la técnica de Bag-Of-Words aplicándola sobre los argumentos previamente procesados (reducción a minúsculas, eliminación de valores numéricos, signos de puntuación y palabras sin significado, además de reducir las palabras a su raiz léxica) y la fución ```cosine_similarity``` de *Scikit-Learn* para el cálculo de similaridad entre las películas.

Las principales desventajas de éste sistemas de recomendación son:

- Se tienen en cuenta palabras que no tienen significado y aparecen repetidas veces (conjunciones, artículos, etc). Este problema se intenta solventar con ayuda de la libreria *NLTK* con sus bases de datos podemos identificar y eliminar las *Stop_Words*.

- El otro problema que radica en el uso de esta técnica son las recomendaciones erroneas que se genran al comparar textos de estensión muy distinta. Los textos a analizar tienen una extensión muy similar por lo que se ignorará esta fuente de error.

Para añadir un grado más de precisión se han reducido las palabras de los argumentos a su raíz léxica y poder así encontrar relaciones entre palabras de la misma familia léxica.

### **Sist. Recomendación Personalizado**

Aplicando el anterior sistema de recomendación se obtendrían las mismas recomendaciones para cualquier usuario que haya vista o gustado cierta película.

Teniendo como datos de entrada una lista de películas que ha visto un usuario de las cuales ha dado una valoración de 1-5 podemos estimar el rating que éste usuario le daría al resto de peliculas del dataset y recomendarle al usuario una lista de películas con el rating estimado mas elevado.



