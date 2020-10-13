---
title: Tarea 2
created: '2020-10-12T22:50:40.829Z'
modified: '2020-10-13T05:10:50.068Z'
---

# Tarea 2
1. Escribe la expresión regular que represente al lenguaje en {a, b, c}* cuyas cadenas contengan una consonante en la penúltima posición.

- Para que la penúltima posición tenga una consonante, se debe considerar las opciones b y c junto con el caso de que posición final puede ser cualquier otro elemento del lenguaje: $(b+c)(a+b+c)$

- Ahora, para considerar los casos, se debe incluir todas las demás posibilidades del lenguaje, es decir: $(a+b+c)^*$

Por lo tanto, mi respuesta es: $(a+b+c)^*(b+c)(a+b+c)$

2. Escribe la expresión regular del lenguaje en {a,b,e}* tal que las cadenas no contienen dos vocales consecutivas

- Primero, para evitar la existencia de dos vocales consecutivas, debo separarlas por el único elemento de mi lenguaje que no es una vocal: $((a+e)b)^*$

- Ahora, debo considerar los casos en los que se repite la sucesión de b, por lo que debo agregar:
$b^*$

- Al juntar ambas expresiones me queda $((a+e)b)^*+b^*$, sin embargo, puedo juntar ambas expresiones y reescribirlo como: $(((a+e)b)+b)^*$

***************************************************************************************************
3. Escribe  la expresión regular que  represente al lenguaje  en {0,1}* cuyas cadenas contengan al menos dos 0 y cuando mucho un 1

- Primero, quiero considerar la posibilidad de tener un 0 o un 1: $(1+0)$

- Despues, debo considerar el hecho de que puede contener al menos dos ceros, por lo que añado: 00.

- Sin embargo, también tengo que contemplar los casos: $001$ y $00000001$, por lo que debo de añadir un prefijo con un $0^*$ y un sufijo de $0^*$, aunque cabe aclarar que la posición de los 2 ceros fijos importa al momento de sacar $001$, $100$, $010$, por lo que hay que considerar tres tipos de limites
- Y ya para al considarar todo, me queda la expresión: $00^*(1+0)00^* + (1+0)000^* + 000^*(1+0)$
***************************************************************************************************
4. Escribe la expresión regular que represente al lenguaje en {0,1}* cuyas cadenas no inician con “00” niterminan con “01”.

- Primero, considero los casos en los que se inicia con 01, 10, 11: $(01+10+11)$

- Después, considero todo lo que se puede conformar con el lenguaje {0,1}: $(0+1)^*$

- Y por último, considero los cosas que conforman 00, 10, 11: $(00+10+11)$

- Y con eso, me queda la expresión: $(01+10+11)(0+1)^*(00+10+11)$

5. Escribe  la  expresión  regular  que  represente  al  lenguaje  en {a,  b,  c}*  cuyas  cadenas  inician y  terminan con el mismo símbolo.

- Primero, considero los elementos del lenguaje como casos: $a + b + c$

- Prosigo incluyendoles a todos la posibilidad de seguir por todos los conjuntos del lenguaje completo: $(a+b+c)^*$

- Y por último, incluyo la concatenación del primer elemento al final, por lo quedaría: $a(a+b+c)^*a+b(a+b+c)^*b+c(a+b+c)^*c$

6. Escribe la expresión regular que represente el lenguaje de todas las cadenas que pueden formarse utilizando los números {1,2,3} donde cada cadena debe contener un único grupo de dos o más 3 consecutivos. Por ejemplo: 12333312, 22133, 13232111333323123

7. Escribe la expresión regular correspondiente al lenguaje de números binarios que sean múltiplos de 4.

8. Escribe la expresión regular que represente al lenguaje en {0,1}* cuyas cadenas que inician con “0” son de longitud par,  y las cadenas que inician con “1” son de longitud impar.
- En el caso de que inicie con $1$ - longitud impar: $1(1+0)*$
- En el caso de que inicie con $0$ - longitud par: $0(1+0)((1+0)(1+0))*$
- Por lo tanto la expresión final quedaria: $1(1+0)* + 0(1+0)((1+0)(1+0))*$

9. Para  cada  una  de  las  siguientes  expresiones  regulares,  escribir  una  cadena  de  longitud  mínima  de  5  que pertenezca al lenguaje y una cadena que no pertenezca.
a. $1* (0+10*) 0*$
- Pertence: $10100$
- No pertenece: $11111$

b. $(1 + 0)*10 (1 + 0)*$
- Pertenece: $11011$
- No pertenece: $11111$

10. Considera  las  siguientes  expresiones  regulares  A y  B  que  representan  lenguajes  en  {a,b}* y  proporciona  un ejemplo de al menos una longitud de 5 caracteres que cumpla con las condiciones de los incisos:
A = $a*(baa*)*b*$                  
B = $b*(a+ba)*b*a$ 
a. Pertenezca al lenguaje A pero no al B
En este caso, se pueden formar las mismas expresiones con B, ya que las cerraduras del clint dan la suficiente flexibilidad para lograrlo, sin embargo, en el caso contrario al tener una a estatica hace que la expresión B pueda formar $baaaaa$, cosa imposible con la expresión A, ya que empezaria a repetir el patrón $baabaa$.

b. Pertenezca a ambos lenguajes
$$baabaa$$

c. No pertenezca a ninguno de los dos 
$$baaab$$ ya que la expresión a no puede formar más de 3 $a$ después de una $b$ y  
