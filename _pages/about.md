---
permalink: /about/
title: "INDICE DE PRECIOS AL CONSUMIDOR SIN ESTACIONALIDAD (IPCse)"
header:
  image: /assets/images/header-git4.jpg
---

yearactual <- 2022

```

## RESULTADOS DICIEMBRE 2022

**El Índice de Precios al Consumidor nacional sin estacionalidad (IPCse) aumentó un 5.4 por ciento en diciembre, luego de haber aumentado también un 5.4 por ciento en noviembre.**<br>

En diciembre los factores estacionales ayudaron a que la medición oficial de la inflación fuera 0.3 puntos porcentuales menor que sin estacionalidad. Durante los últimos 12 meses, el índice aumentó un 94.8 por ciento antes del ajuste estacional (datos oficiales de INDEC).<br>

Durante diciembre, salvo en la región noreste, en las cinco regiones restantes la estacionalidad hizo que la medición oficial fuera de entre 0.1 y 0.4 puntos porcentuales menor al índice sin estacionalidad.En la región noreste la estacionalidad hizo que el dato oficial fuera 0.2 puntos porcentuales más grande que sin estacionalidad (Figura 1).<br>

**Los índices de precios de bebidas alcohólicas y tabaco y de restaurantes y hoteles fueron, con diferencia, los que más aumentaron en el mes.** En un segundo escalón estuvieron los incrementos en equipamiento y mantenimiento del hogar y educación. Los índices de precios de alimentos y bebidas no alcohólicas; vivienda, agua, electricidad, gas y otros combustibles; comunicación y recreación y cultura aumentaros por debajo del nivel general desestacionalizado (Cuadro 1).<br>

La estacionalidad contribuyó a que el índice oficial de la división de prendas de vestir y calzado fuera 1.1 puntos porcentuales menor a lo que hubiera dado la inflación del mismo índice ajustado por estacionalidad. En el caso del índice de precios de la división de educación la estacionalidad también hizo que el valor oficial fuera menor, 2.5 puntos porcentuales, a la inflación que se hubiera producido sin estacionalidad. El impacto estacional tuvo el efecto contrario en el índice de precios de la división de comunicación donde el valor oficial fue 0.7 puntos porcentuales más alto de lo que hubiera sido sin estacionalidad. En términos interanuales, antes del ajuste estacional, los índices de precios de la división de prendas de vestir y calzado y restaurantes y hoteles se incrementaron más del 100 por ciento (Figura 2).<br>

**La contribución más importante al dato del nivel general del IPCse de diciembre la hizo el índice de precios de la división alimentos y bebidas no alcohólicas explicando 1.37 puntos porcentuales del 5.4 por ciento de inflación.** Prendas de vestir y calzado con 0.61 puntos porcentuales, transporte con 0.66 y restaurantes y hoteles con 0.67 puntos porcentuales fueron las otras divisiones importantes en el aumento del nivel general de precios sin estacionalidad. El índice de precios de la división alimentos y bebidas no alcohólicas contribuyó en más de 1 punto porcentual en todas las regiones del país excepto en la región de Cuyo dónde la mayor contribución a la inflación de diciembre de esa región fue el transporte (Cuadro 2).<br>

**En la comparación interanual, diciembre de 2022 contra diciembre de 2021 antes del ajuste estacional, más del 50 por ciento del aumento de 94.8 por ciento está explicado por los índices de precios de tres de las divisiones de la canasta: alimentos y bebidas no alcohólicas, prendas de vestir y calzado y transporte.** Salud con una incidencia interanual de 8 puntos porcentuales y restaurantes y hoteles con una contribución de casi 7 puntos porcentuales son las divisiones que le siguen en explicación del aumento interanual del nivel general de precios (Cuadro 2).<br> 

**En diciembre, la inflación subyacente, definida como el cambio porcentual en el nivel general del IPCse menos el efecto de los índices de precios de las divisiones de la canasta que incluyen bienes y servicios regulados o con alto componente impositivo, fue de 5.4 por ciento después de haber aumentado un 5 por ciento en noviembre.**  El valor de diciembre fue impulsado por la región del GBA. En términos interanuales, antes del ajuste estacional, la inflación subyacente en las regiones de GBA y patagónica superaron el 100 por ciento (Cuadro 1).


```{r excel, message=FALSE,echo=FALSE}

cuadro1 <- read_excel("/assets/images/IPCse_01_23.xlsx", 
                      sheet = "Cuadro1", range = "E47:L74", 
                      na = "NA")
colnames1 <- colnames(cuadro1)
colnames1[1] <- " "
colnames(cuadro1) <- colnames1


cuadro2 <- read_excel("/assets/images/IPCse_01_23.xlsx", 
                      sheet = "Cuadro2", 
                      range = "D13:K46")

figura1 <- read_excel("/assets/images/IPCse_01_23.xlsx", 
                      sheet = "Figura1", 
                      range = "D47:G61")

figura2 <- read_excel("/assets/images/IPCse_01_23.xlsx", 
                      sheet = "Figura1", 
                      range = "D63:F87")
```

<br>

---

<br>

```{r cuadro1, echo=FALSE, message=FALSE}
yearscuadro1 <- c("",as.character(cuadro1[1,2:7]),"2022/2021")

colnames(cuadro1)[8] <- "  "

# Tengo que automatizar la barrita que dice 

cuadro1 %>%   
  slice(-1) %>%
  kable(caption = "**Cuadro 1.  Cambios porcentuales en el IPCse**", digits=1, align = c('l',rep('c',times=7))) %>%
  row_spec(1,bold=TRUE) %>% 
  group_rows("Regiones", 2,7) %>%
  group_rows("Divisiones COICOP", 8,19) %>%
  group_rows("Inflación subyacente", 20,26) %>%
  column_spec(column=1:8, extra_css = "vertical- align:middle;") %>%
  kable_styling() %>%
  add_header_above(c("Año"=1, "2022"=6, "Dic. 2022/Dic. 2021"=1)) %>%
  add_header_above(c("IPCse" = 1, "Variación mensual" = 6, "Variación interanual" = 1)) 
```

<br>
 
---

<br> 

<span style="color:#777;font-size:13    .0pt;"> **Figura 1. Tasa de inflación mensual**</span>

```{r figura1, message=FALSE,echo=FALSE} 
fg1 <- figura1 %>%
  mutate_if(is.numeric, ~round(.,1)) %>%
  rename(Variacion = Dato)

fg1$Region <- fct_relevel(fg1$Region, c("Patagonia", "Cuyo", "Noreste", "Noroeste", "Pampeana" ,"GBA","Nacional"))

g1 <- ggplot(fg1, aes(x=Region, y=Variacion, fill=Serie)) +
  geom_bar(stat="identity", width = 0.5, position = "dodge") +
  scale_fill_manual(values=c("#111C7F","#CB2B00")) +
  labs(y = "Variación porcentual",
       x = "") +
  coord_flip() 

ggplotly(g1)

```

<br>

---

<br>

<span style="color:#777;font-size:13    .0pt;"> **Figura 2. Tasa de inflación mensual en cada división COICOP**</span>


```{r figura2, message=FALSE,echo=FALSE} 

fg2 <- figura2 %>%
  mutate_if(is.numeric, ~round(.,1)) %>%
  rename(Variacion = Dato)

fg2$Division <- fct_relevel(fg2$Division,c("Bienes y servicios varios", "Restaurantes y hoteles", "Educación", "Recreación y cultura", "Comunicación", "Transporte", "Salud", "Equipamiento y mantenimiento del hogar", "Vivienda, agua, electricidad, gas y otros combustibles", "Prendas de vestir y calzado", "Bebidas alcohólicas y tabaco", "Alimentos y bebidas no alcohólicas"))

g2 <- ggplot(fg2, aes(x=Division, y=Variacion, fill=Serie)) +
  geom_bar(stat="identity", width = 0.5, position = "dodge") +
  scale_fill_manual(values=c("#111C7F","#CB2B00")) +
  labs(y = "Variación porcentual",
       x = "") +
  coord_flip() 

ggplotly(g2, height = 800)

```

<br>

---

<br>
```{r cuadro2, echo=FALSE, message=FALSE}

colnames2 <- colnames(cuadro2)
colnames2[1] <- " "  
colnames(cuadro2) <- colnames2
  
cuadro2 %>%   
  slice(c(2,5:17,19,22:33)) %>%
  kable(caption = "**Cuadro 2. Incidencia de las divisiones en la inflación**",
        digits=1, align = c('l',rep('c',times=7))) %>%
  row_spec(c(1,15),bold=TRUE) %>% 
  kable_styling() %>%
  group_rows("Incidencia con respecto al mismo mes del año anterior", 1,14) %>%
  group_rows("Incidencia con respecto al mismo mes del año anterior", 15,27) %>%
  add_footnote("Nota: los ponderadores de los índices de precios de las divisiones para el cálculo de las incidencias del IPC nacional se construyeron como promedio ponderado de las ponderaciones regionales al no existir ponderadores oficiales. Debido a esto, el resultado de la suma de las incidencias da un valor aproximado a la inflación del nivel general.",notation="symbol")

```


<br>

---

<br>


## NOTA TECNICA

### Breve explicación del IPCse

El Índice de Precios al Consumidor (IPC) que publica mensualmente el Instituto de Estadística y Censos (INDEC) mide el cambio en los precios de una canasta de bienes y servicios adquiridos por los consumidores urbanos. El índice mide cambios de precios con respecto a una fecha de referencia. La fecha de referencia es diciembre de 2016 donde el IPC vale 100. El INDEC publica índices de precios, para diferentes regiones del país y para el total nacional, que no están ajustados por estacionalidad.  

Para analizar la evolución de los índices de precios en el corto plazo, los cambios desestacionalizados suelen preferirse ya que eliminan los efectos que normalmente ocurren en la economía, al mismo tiempo y en aproximadamente la misma magnitud cada año. Estos efectos producen movimientos de precios resultantes de fenómenos meteorológicos, ciclos de producción, vacaciones, cambios de estación, etc.  

El ajuste estacional elimina los efectos de estas características recurrentes que se repiten en la misma época todos los años. El proceso de ajuste cuantifica los patrones estacionales y luego los excluye del índice para permitir el análisis de movimientos de precios sin estos efectos. Las condiciones climáticas cambiantes, los ciclos de producción, las festividades pueden causar variaciones estacionales en los precios y estos movimientos estacionales pueden ser diferentes en cada una de las regiones en las que se divide el país. Por ejemplo, en la región cuyana el índice de precios de la división de recreación y cultura no presenta estacionalidad mientras que en la región del Gran Buenos Aires (GBA) sí; en la región patagónica el índice de precios de la división de restaurantes y hoteles presenta una clara estacionalidad mientras que el mismo índice en la región pampeana no la tiene.
¿Para qué se utiliza un IPC sin estacionalidad? En general, se utiliza para analizar las tendencias generales de precios en la economía en el corto plazo. Los datos desestacionalizados suelen usarse en la formulación de la política económica y en la investigación económica porque eliminan los efectos de los cambios que normalmente ocurren al mismo tiempo y en aproximadamente la misma magnitud cada año. En Argentina, el INDEC desagrega el IPC en categorías, una de las cuales, “Estacionales”, contiene el efecto estacional de todos aquellos precios de productos que contienen estos movimientos. En lugar de separar los efectos estacionales el IPCse retiene todos los bienes y servicios de la canasta que adquieren los consumidores urbanos y les elimina los factores estacionales a los índices de precios de las divisiones de la canasta que los tienen.  

La inflación subyacente se define como la que se obtiene con el IPCse sin el efecto de los índices de precios de las divisiones que contienen los productos regulados o con alto contenido impositivo. En este sentido, la inflación subyacente cumple una función similar a la del denominado IPC núcleo, que calcula el INDEC, excluyendo del nivel general bienes y servicios los estacionales y los regulados. Una diferencia con relación a la inflación núcleo es que en lugar de excluir los precios estacionales, la inflación subyacente los retiene pero les quita la estacionalidad. Una diferencia adicional es que como el IPCse se calcula en base a los datos publicados por el INDEC no puede desagregar los índices de precios de las divisiones que componen la canasta para analizar la estacionalidad de los grupos, clases, subgrupos, y productos que componen cada división.  

**¿Cómo se ajustan estacionalmente los índices de precios?** 

El movimiento estacional en el nivel general del índice de precios de cada región del país se elimina desestacionalizando cada uno de los índices de las 12 divisiones de la canasta de bienes y servicios de cada región. Después, estos índices desestacionalizados se agregan utilizando los ponderadores publicado por INDEC para las divisiones en la fecha de referencia del IPC: diciembre de 2016. Las divisiones representan los agrupamientos de la Clasificación del Consumo Individual por Finalidad (Classification of Individual Consumption According to Purpose, COICOP, por sus siglas en inglés) elaborada por la Comisión de Estadísticas de las Naciones Unidas (1999) y adaptada por INDEC en 2019.   

Los índices regionales sin estacionalidad construidos de esta manera se agregan para determinar el IPCse nacional. Para la agregación de los índices de precios regionales nuevamente se utilizan los ponderadores del índice en la fecha de referencia: diciembre de 2016.  

Para desestacionalizar el IPCse se utiliza el software de ajuste estacional X-13ARIMA-SEATS (promedio móvil integrado autorregresivo) desarrollado por la Oficina del Censo de EE. UU. en 2013. El X-13ARIMA-SEATS utiliza el método de ajuste estacional X-11 junto con el modelo de regresión ARIMA para el análisis de intervención y la proyección de datos. El análisis de intervención se utiliza en el ajuste estacional de los índices de precios al consumidor para proporcionar datos del IPC más precisos. En este sentido, el procedimiento trata de compensar los efectos que la extrema volatilidad de los precios pudiera tener en las estimaciones y proyecciones de los factores estacionales.  

El análisis de intervención es el ajuste previo de cada serie de índices antes del cálculo de los factores estacionales. Es posible que se requiera un ajuste previo si se produce un cambio de nivel o un valor atípico. Un cambio de nivel ocurre cuando un bien o servicio experimenta un cambio único, grande y rápido en el nivel de precios. Un valor atípico es un valor extremo para algún mes en particular. Ejemplos recientes de estos potenciales cambios de nivel/valores atípicos pueden verse en los meses en los cuales debido a la pandemia del COVID-19 la política de Aislamiento Social Preventivo y Obligatorio (ASPO) obligó a un cambio de metodología en la recolección de precios (de presencial a no presencial) además de provocar imputaciones por falta de precios de algunos bienes y servicios (restaurantes y hoteles, por ejemplo). La eliminación de estos valores atípicos produce un patrón estacional más claro y da como resultado factores estacionales más estables y que se “ajustan” mejor a la serie histórica. Luego, los factores estacionales se aplican a los datos no ajustados (sin ningún ajuste previo) para calcular el índice ajustado estacionalmente.  

Para construir el IPCse se utiliza el método de desestacionalización directo para los 12 índices de precios de las divisiones de cada región y luego usa el ajuste estacional indirecto para construir el IPCse de cada región. Por último, con la agregación de los IPC regionales se construye el IPCse nacional, como se mencionó arriba.  

Para determinar si el índice de precios de una división tiene estacionalidad se utilizan las medidas de diagnóstico sobre la calidad y estabilidad de la estacionalidad que tiene el método X-11. El X-11 tiene dos estadísticos F que contrastan la presencia de estacionalidad estable.  Ambos contrastes paramétricos se basan en la estimación del cociente de la varianza “estacional” y la varianza del componente irregular y utilizan diferentes ajustes del componente de tendencia ciclo. Adicionalmente, el método X-11 provee de un contraste no paramétrico de estacionalidad estable, el estadístico chi-cuadrado de Kruskal-Wallis. El X-11 también tiene medidas de estacionalidad móvil. Si hay mucha estacionalidad móvil la serie no es candidata a desestacionalizarse. El método X-11 tiene un contraste de hipótesis que combina el contraste paramétrico y el no paramétrico para detectar la presencia de estacionalidad estable en la serie. Para medir la cantidad de estacionalidad móvil el método también produce el estadístico M7 que mide la cantidad de estacionalidad móvil comparada con la cantidad de estacionalidad estable, a mayor estacionalidad móvil menor probabilidad de obtener patrones estacionales estables. Por último, el X-11 tiene una medida de la calidad del ajuste estacional (el estadístico Q) que es un promedio ponderado de once estadísticos diferentes. El Manual del X-13ARIMA-SEATS contiene una descripción completa de estos estadísticos.  

Para que un índice de precios de una división pueda desestacionalizarse el se usa un criterio muy similar al que utiliza el Bureau of Labor Statistics (BLS) de Estados Unidos en la desestacionalización del Consumer Price Index for All Urban Consumers (CPI-U): contraste paramétrico F≥7; test combinado detectando la presencia de estacionalidad estable además de que los estadísticos M7 y Q sean menores a uno.  

Usando estos criterios los índices de precios de las divisiones de la COICOP: alimentos y bebidas no alcohólicas, bebidas alcohólicas y tabaco, prendas de vestir y calzado y educación tienen estacionalidad en las seis regiones del país. Además de estos índices de precios, en la región del GBA, equipamiento y mantenimiento del hogar, transporte, comunicación y recreación y cultura tienen estacionalidad. En la regiones pampeana y noroeste se detecta estacionalidad estable en comunicación y recreación y cultura.  En la región noreste hay estacionalidad en los índices de precios de equipamiento y mantenimiento del hogar, comunicación, recreación y cultura y bienes y servicios varios. En la región de Cuyo se detecta estacionalidad en las series de comunicación, recreación y cultura y restaurantes y hoteles. Finalmente, en la región patagónica las series con estacionalidad son equipamiento y mantenimiento del hogar, salud, recreación y cultura y bienes y servicios varios.  

Se debe notar que siguiendo estos criterios estadísticos ni el CPI-U de Estados Unidos, ni el IPC nacional tienen estacionalidad, pero incluyen índices de precios más desagregados que sí la tienen. Debido a esto el BLS publica el CPI-U desestacionalizado para analizar las variaciones de precios mes a mes. Para el IPCse se utiliza el mismo procedimiento, se incorpora dentro del IPC a las series desestacionalizadas identificando sus factores estacionales de forma tal de poder cuantificar su impacto mensual, presente y futuro.  

El no detectar estacionalidad estable en el nivel general del índice implica que los patrones estacionales de las series más desagregadas se compensan en el agregado. Hay algunos índices de precios de las 12 divisiones de la canasta que a pesar de tener estacionalidad estable tienen un patrón estacional con una amplitud moderada o baja como son las series de alimentos y bebidas no alcohólicas y bebidas alcohólicas y tabaco. Otros índices de precios como educación y prendas de vestir y calzado tienen una estacionalidad más marcada, pero tienen una menor ponderación en la construcción del nivel general. En la región del GBA por ejemplo, el patrón de estacionalidad de prendas de vestir y calzado es un espejo del de recreación y cultura (con ponderadores parecidos en el nivel general), los picos estacionales de la primera serie coinciden con los valles en la segunda y viceversa.  

Cada mes de enero, con los datos de los índices hasta diciembre se reevalúa la estacionalidad de cada serie de índices con base en los criterios estadísticos mencionados arriba. Un índice podría cambiar su estado de ajuste estacional de “ajustado estacionalmente” a “no ajustado estacionalmente”, o viceversa. A mediados de febrero de cada año, cuando se publican los datos de inflación de enero, el se publicarán nuevos índices ajustados estacionalmente y los nuevos factores de ajuste estacional para cada división. Estos factores de estacionalidad permanecen constantes durante el resto del año. El método X-11 utilizado para el ajuste estacional produce una serie desestacionalizada diferente con cada dato mensual adicional de forma tal que el IPCse debería actualizarse hacia atrás con cada nuevo dato. Para evitar este ajuste mensual en la desestacionalizada los factores estacionales se mantienen constantes durante un año de forma tal de no cambiar hacia atrás la serie sin estacionalidad. Este es el mismo procedimiento que usa el BLS para la construcción del CPI-U desestacionalizado. Cada mes de enero, como se mencionó arriba se actualizan estos factores estacionales y se reconstruye la serie desestacionalizada hasta 5 años hacia atrás. Los factores estacionales de más de 5 años hacia atrás se consideran definitivos.
