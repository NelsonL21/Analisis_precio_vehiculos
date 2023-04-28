# Analisis_precio_vehiculos
En el presente trabajo de investigación se pretende determinar que factores permiten aumentar el precio de los vehículos dependiendo de diversas caracteristicas como el modelo del auto, su año de lanzamiento al mercado, la edad del mismo, su precio de venta, sus millas recorridas, entre otros.

## Conclusión general
En conclusión se pudieron llegar a estudiar en profundidad, que factores son los que pueden afectar el precio de los autos en este caso de estudio.

**Preprocesameinto de datos:**

* En este caso el reto fúe lograr completar los valores ausentes y determinar los tipo de datos a utilizar
  * Primeramente se rellenaron los valores ausentes en alas millas tomando enc uenta la correlación que debe existoir entre el tiepo devida de un auto y cuando recorre este.
  *   Así mismo de cambiaron los valores NAN de las tracción en las 4 ruedas por 0, ya que querian decri falso.
  * Sin embargo, no fué posible rellenar los valores ausnetes en el año del modelo, número de cilindros o el color de la pintura. El año del modelo y número de cilindros son especificaciones de cada modelo, colocarlo basandonos en este y en el año no sería corrcto, ya que puede haber un ford f-150 del 2008 con 4 cilindros o de 8, y que incluso uno del 2010 con 6 u 10 cilindros, por lo que rellenandolo con la media, mediano o moda lo unico que causará será sesgar los datos. Con el color, es una característica arbitraria, no se puede rellenar por las mismas razones antes mencionadas. Por lo que son un mla necesario.
  * Se cambiaron los tipos de dato `float` a `Int64` en el caso de los cilindros y a `DateTime` en el caso del año  de modelo y la fecha de venta.

**Tratamiento de valores atípicos**
* Al realizar los histogramas de las variables númericas de la tabla principal, se observó la gran canridad de atípicos que habian. Cosa que no es de extrañar cuando de autos se refiere, ya que hay muy antiguos que valen mucho o poco, así como carros muy caros o muy económicos. Lo que se hizo fué mediante gráficos de caja y bigotes determinar que valores estaban fuera de rango y truncar la data almacenandola en otro DataFrame.
  * Se deciciío que el precio debia oscilar entre 1000 y 50000, ya que precios inferiores no hacen sentido y superiores son demasiado atípicos para la clase media alta, como para considerarlos en el análisis.
  * Se decidió Truncar los años de 20años hacia abajo, ya que el resto son muy viejos, y pueden perjudicar el análisis, ya que son carros que no compra el común denominador de las personas.
  * Se truncó el millaje a un máximo de 300000 millas, ya que por encima son basatent dificiles de vender y probablemente signifique que es un auto viejo, o que lo han usado demasiado, por lo que es de más cuidado.
  * El resto de columnas no se considera que tuvieran atípicos.

**Análisis del precio**

* Se llegó a la conclusión que los dos autos más publicados son el ford f-150 y el chevrolet silverado 1500, Así mismo, los valores que más contribuyen a las fluctuaciones en el precio son:
  * Los factores numéricos que más influyen en el precio, son el millaje, el cual es inversamnete proporcional, entre más millas tiene un carro recorridas, menor será el precio, de la misma manera que con la edad del auto. Sin embargo la correlación entre estos no es tan fuerte, como para considerarse como tal.
  * Podemos observar, que el color de los autos no es un factor demasiado determinante en lo que aumentar el valor de un auto se refiere. De hecho los mantiene en un valor mediano de unos 10000. Sin embargo observando los graficos obtenidos, podemos ver que los colores que más venden los autos, y que efectivamente aumentan el precio de estos son el blanco, el negro y un tanto el rojo.
  * Tener una transmisión hibrida si es un factor determinante que aumenta el precio de los autos, sin embargo la automatica en promedio esta u poco por encima de la manual.
  * Tener un auto a diesel es un factor bastanet determinante que aumenta mucho el precio de los autos, debido a que este es más economico en muchos paiese y por lo tanto más solicitados.
  * También podemos observar que los autos que más aumentan el precio de los mismos, son los tipo, tractor, pickup, dependiendo del tipo de coupe, y los convertibles.
  * Por último los carros con tracción de 4 ruedas definitivamente aumentan el precio de estos.
