# Buenas prácticas en Java

En este documento se muestran buenas prácticas al momento de programar en Java.
Estas prácticas no son obligatorias, pero sí muy recomendadas, debido a que hacen que el código sea más legible y comprensible.

## Fuentes de información

La información de esta guía fue obtenida de las siguientes fuentes:

* https://www.oracle.com/technetwork/java/codeconventions-150003.pdf
* https://www.codejava.net/coding/10-java-core-best-practices-every-java-programmer-should-know
* https://www.programaenlinea.net/10-buenas-practicas-en-java-que-debes-conocer/
* https://stackoverflow.com/questions/541912/interface-naming-in-java
* https://www.javatpoint.com/java-naming-conventions
* https://decodigo.com/2013/04/mejores-practicas.html
* https://lecasabe.com/buenas-practicas-en-java/
* https://unpocodejava.com/2012/03/16/buenas-practicas-de-codificacion-en-java/
* https://www.clubdetecnologia.net/blog/2017/java-buenas-practicas-para-el-manejo-de-excepciones/

## Convenciones de nomenclatura

Los nombres deben ser autoexplicativos, es decir, explicarse por sí mismos.
Los nombres ```x``` o ```str``` no explican nada, al contrario de identificadores como ```edad``` o ```nombre```.
Si un nombre requiere un comentario para explicar su significado, entonces su nombre no es autoexplicativo.
En contextos matemáticos o científicos puede ser aceptable usar identificadores cortos en algunas secciones.

Si dos o más nombres son distintos, esta diferencia debería ser significativa.
Los nombres ```a1``` y ```a2``` son distinciones sin sentido, nombre como ```origen``` y ```destino``` tienen distinciones significativas.

Los nombres deben ser pronunciables naturalmente en el idioma en el que se escriben y ser fáciles de recordar.
Por ejemplo se puede comparar ```buscPers``` con ```buscarPersona```.

Se debe evitar el uso de acrónimos, a no ser que estos sean populares.
Ejemplos de acrónimos populares incluyen ```HTML```, ```CSV```, ```JSON```, ```SQL```, etc.
Se debe evitar el uso de abreviaturas

## Escritura de nombres

Los nombres de paquetes deberían ser sustantivos cortos escritos en ```lowecase```.

Los nombres de clases deberían ser sustantivos escritos en ```PascalCase```.

Los nombres de interfaces deberían ser sustantivos o adjetivos escritos en ```PascalCase```.

Los nombres de variables deberían ser sustantivos o adjetivos escritos en ```camelCase```.

Los nombres de métodos deberían ser verbos escritos en ```camelCase```.

Los nombres de constantes deberían ser sustantivos escritos en ```UPPER_SNAKE_CASE```.

## Orden de atributos

Los atributos de una clase deberían ordenarse según su modificador de acceso, del más restrictivo al menos restrictivo (```private```, ```local```, ```protected```, ```public```).
Los atributos de un mismo modificador de acceso deberían ordenarse alfabéticamente.



## Atributos públicos

Se recomienda minimizar el número de atributos públicos lo máximo posible

```

```

## Uso de guiones bajos al escribir números

## Evitar bloques catch vacíos

## Errores de los Scanner

## StringBuilder o StringBuffer en vez de concatenación

## Inicialización redundante

## Uso de bucles for each con arreglos

## Inferencia de tipos

## Usar List para instanciar listas

## Inicializar colecciones con tamaño aproximado

## La recursión puede ser conveniente

## Evitar llamadas a métodos dentro de las condiciones de bucles

## Trazas de depuración