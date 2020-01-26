Traducido por [@FiliBits](https://github.com/Filibits)

# Flexbox30

Aprenda Flexbox en 30 días con 30 tidbits (golosinas) de código ✨

<img src="../flexbox30-cover.png" alt="Flexbox Cover" width="350">

## Tabla de Contenidos

1. [Introducción](#flexbox-intro)
1. [Contenedor Flex & Elementos Flex](#flex-container-and-flex-items)
1. [Solo un hijo inmediato](#immediate-child-only)
1. [Ejes de Flexbox](#flexbox-axes)
1. [Módulo Flexbox](#flexbox-module)
1. [Propiedades del padre](#parent-properties)
1. [Display](#display)
1. [block vs inline](#block-vs-inline)
1. [flex-direction](#flex-direction)
1. [flex-wrap](#flex-wrap)
1. [flex-flow](#flex-flow)
1. [justify-content [row]](#justify-content-row)
1. [justify-content [column]](#justify-content-column)
1. [space-around vs space-evenly](#space-around-vs-space-evenly)
1. [align-items [row]](#align-items-row)
1. [baseline](#baseline)
1. [align-items [column]](#align-items-column)
1. [align-content](#align-content)
1. [Propiedades del hijo](#child-properties)
1. [order](#order)
1. [flex-grow](#flex-grow)
1. [flex-grow (cálculo)](#flex-grow-calculation)
1. [flex-shrink](#flex-shrink)
1. [flex-shrink (cálculo)](#flex-shrink-calculation)
1. [flex-basis](#flex-basis)
1. [flex-basis vs width](#flex-basis-vs-widths)
1. [flex](#flex)
1. [align-self](#align-self)
1. [Propiedades de Flexbox](#flexbox-properties)
1. [Hoja de trucos para Flexbox](#flexbox-cheatsheet)
1. [Alineación con márgenes automáticos](#auto-margins)
1. [Recursos](#resources)
1. [Di Hola](#say-hello)
1. [Descarga y Comparte](#download-and-share)
1. [Contribución](#contribution)
1. [Licencia](#license)

## Conceptos básicos de Flexbox

<a id="flexbox-intro"></a>

### [Día 1: Introducción](#flexbox-intro)

Antes de Flexbox, usábamos principalmente floats para el diseño. Y para aquellos desarrolladores de CSS, todos conocemos las frustraciones y limitaciones de la antigua forma -- especialmente la capacidad de centrarse verticalmente dentro de un padre. ¡Ugh, eso fue tan molesto! ¡Ya no! ¡Flexbox para la victoria!

<p><img src="../code-tidbits/1-flexbox-intro.png" alt="Flexbox Introduction" width="500"></p>

<a id="flex-container-and-flex-items"></a>

### [Día 2: Contenedor Flex & Elementos Flex](#flex-container-and-flex-items)

Para que Flexbox funcione, debe configurar la relación padre-hijo. El padre es el contenedor flex, y todo lo que contiene son los hijos o elementos flex.

<p><img src="../code-tidbits/2-flex-container-and-flex-items.png" alt="Flex Container & Flex Items" width="500"></p>

<a id="immediate-child-only"></a>

### [Día 3: Solo un hijo inmediato](#immediate-child-only)

Una cosa MUY importante que quiero señalar es que el contenedor flex solo se envuelve alrededor de sus hijos inmediatos. El contenedor flex no se envuelve más allá de una capa de profundidad. Solo los hijos inmediatos. Entonces NO hay una relación de nietos o bisnietos. ¡Solo padres ↔️ hijos inmediatos!

Por supuesto, puede establecer un Flexbox siempre que haya una relación padre-hijo. Por lo tanto, un hijo también puede ser el contenedor flex para sus hijos. Pero será un contenedor flex separado. Y no transfiere las propiedades de Flexbox a los abuelos.

Este es probablemente uno de los conceptos más importantes que me ayudó a comprender cómo funciona Flexbox. Y saber esto ayudará a resolver muchos de esos momentos "oye, ¿por qué no funciona?" 😅

<p><img src="../code-tidbits/3-immediate-child-only.png" alt="Immediate Child Only" width="500"></p>

<a id="flexbox-axes"></a>

### [Día 4: Ejes de Flexbox](#flexbox-axes)

Flexbox opera en un sistema de 2 ejes: uno principal y un eje transversal. El eje principal define la dirección de cómo se colocan sus elementos flex en el contenedor flex. Determinar el eje transversal es muy simple, está en la dirección que es perpendicular a su eje principal.

Recuerdas que en la clase de matemáticas, nos enseñaron con los ejes **x** y **y**. Bueno, tíralo. Porque el eje principal puede ser horizontal o vertical. El eje **x** no siempre es el eje principal. Cometí un error, así que espero que no hagas la misma suposición incorrecta que yo 😅

<p><img src="../code-tidbits/4-flexbox-axes.png" alt="Flexbox Axes" width="500"></p>

<a id="flexbox-module"></a>

### [Día 5: Módulo Flexbox](#flexbox-module)

Acerquémonos a uno de los diseños y veamos la anatomía de Flexbox. En cada eje, hay un comienzo y un final. Si está en el eje principal, la posición inicial se llama **main start** (inicio principal) y si la posición final se llama **main end** (final principal). El mismo concepto se aplica al eje transversal. Conocer su inicio y final es importante porque puede controlar dónde se colocan sus elementos flex.

Y esto concluye nuestros Fundamentos de Flexbox.

<p><img src="../code-tidbits/5-flexbox-module.png" alt="Flexbox Module" width="500"></p>

**[⬆ volver arriba](#tabla-de-contenidos)**

## Propiedades del padre

<a id="parent-properties"></a>

### [Día 6: Propiedades del padre](#parent-properties)

Ahora sabe que flex opera en una relación padre-hijo. Entonces tenemos 2 entidades involucradas para comenzar este tango. Y cada entidad tendrá su propio conjunto de propiedades CSS únicas que se pueden aplicar a ellas. Por eso es importante que sepa qué elemento es el padre y qué elemento(s) es el hijo. Comencemos con las propiedades principales 🤰


<p><img src="../code-tidbits/6-parent-properties.png" alt="Parent Properties" width="500"></p>

<a id="display"></a>

### [Día 7: Display](#display)

Para comenzar esta fiesta de Flexbox, primero debemos crear nuestro contenedor flex. Esto se realiza aplicando `flex` a la propiedad `display` en el elemento padre. ¡Bam! Ahora todos sus hijos inmediatos se convertirán en elementos flex 🎊.

Hay 2 tipos de contenedor en Flexbox: `flex` creará un contenedor flex de tipo *block*. E `inline-flex` creará un contenedor flex de tipo *inline*. Más de *block* e *inline* mañana 😉

<p><img src="../code-tidbits/7-display.png" alt="Display" width="500"></p>

```css
.padre {
  display: flex /* por defecto */
         o inline-flex
}
```

<a id="block-vs-inline"></a>

### [Día 8: block vs inline](#block-vs-inline)

Explicado de manera muy simple, el elemento `block` ocupa todo el ancho del contenedor. Parecen bloques de construcción donde cada bloque está apilado unos sobre otros. Mientras que el elemento `inline` solo ocupa el espacio que necesita. Entonces parecen estar en una línea, o uno al lado del otro.

<p><img src="../code-tidbits/8-block-vs-inline.png" alt="block vs inline" width="500"></p>

<a id="flex-direction"></a>

### [Día 9: flex-direction](#flex-direction)

Esta es la propiedad que nos permite definir nuestro eje principal. Recuerde que mencioné que nuestro eje principal puede ser horizontal o vertical. Entonces, si queremos que el eje principal sea horizontal, usamos **row**. Y si queremos que sea vertical, usamos **column**. Además, recuerde que tuvimos un **main start** (inicio principal) y **main end** (final principal). Simplemente agregamos el sufijo `reverse` para establecer nuestro "main start" en la dirección inversa. Genial eh 👍

<p><img src="../code-tidbits/9-flex-direction.png" alt="flex-direction" width="500"></p>

```css
.padre {
  flex-direction: row /* por defecto */
                o row-reverse
                o column
                o column-reverse
}
```

<a id="flex-wrap"></a>

### [Día 10: flex-wrap](#flex-wrap)

Por defecto, los elementos flex tratarán de encogerse para que quepan en una línea, en otras palabras, `no wrap`. Sin embargo, si desea que los elementos flex mantengan su tamaño y que el desbordamiento se extienda en varias líneas en los contenedores, puede activar `wrap`.

Esta propiedad es lo que permitirá que los artículos flex ocupen más de una línea en su contenedor.

<p><img src="../code-tidbits/10-flex-wrap.png" alt="flex-wrap" width="500"></p>

```css
.padre {
  flex-wrap: nowrap /* por defecto */
           o wrap
           o wrap-reverse
}
```

<a id="flex-flow"></a>

### [Día 11: flex-flow](#flex-flow)

Así que hemos aprendido `flex-direction` y` flex-wrap`. ¡Si entiendes esos 2, obtendrás `flex-flow`! Porque es solo una abreviatura de estas dos propiedades 👏

Puede establecer ambas propiedades al mismo tiempo. O simplemente puedes pasar uno de ellos. El valor predeterminado es `row nowrap`. Entonces, si solo establece un valor, la propiedad que no se estableció tomará el valor predeterminado.

<p><img src="../code-tidbits/11-flex-flow.png" alt="flex-flow" width="500"></p>

```css
.padre {
  flex-flow: row nowrap /* por defecto */
           o <flex-direction> <flex-wrap>
           o <flex-direction>
           o <flex-wrap>
}
```

<a id="justify-content-row"></a>

### [Día 12: justify-content [row]](#justify-content-row)

Aquí viene la parte divertida. Esta es la propiedad que establece la alineación a lo largo del eje principal. En este ejemplo, el eje principal se encuentra horizontalmente. En otras palabras, flex-direction se establece en `row`.

Esta es probablemente mi propiedad principal más utilizada. Simplemente elija el diseño que desee y BAM Flexbox lo hace automáticamente por usted. Y es absolutamente responsivo. A medida que aumenta o reduce el ancho de la ventana, Flexbox hará el cálculo detrás de escena y se asegurará de que se mantenga el diseño elegido. Es como uno de esos electrodomésticos de cocina donde "lo configuras y lo olvidas" 🍗

<p><img src="../code-tidbits/12-justify-content-row.png" alt="justify-content row" width="500"></p>

```css
.padre {
  justify-content: flex-start /* por defecto */
                 o flex-end
                 o center
                 o space-around
                 o space-between
                 o space-evenly
}
```

<a id="justify-content-column"></a>

### [Día 13: justify-content [column]](#justify-content-column)

El eje principal también puede estar en posición vertical. En ese caso, flex-direction se establece en `column`. Así es como se alinearán los elementos flex en esa instancia.

<p><img src="../code-tidbits/14-justify-content-column.png" alt="justify-content column" width="500"></p>

```css
.padre {
  flex-direction: column;
  
  justify-content: flex-start /* por defecto */
                 o flex-end
                 o center
                 o space-around
                 o space-between
                 o space-evenly
}
```

<a id="space-around-vs-space-evenly"></a>

### [Día 14: space-around vs space-evenly](#space-around-vs-space-evenly)

Es posible que no note la sutil diferencia entre space-around y space-evenly. Entonces hablemos de eso. En `space-evenly`, el espacio vacío entre los elementos flex siempre es igual. Sin embargo, en `space-around`, solo los elementos internos tendrán el mismo espacio entre ellos. El primer y último elemento solo se le asignará la mitad del espacio. Dando la apariencia visual de que está más extendido. Se puede decir que a estas personas les gusta vivir la vida al límite 😂

<p><img src="../code-tidbits/13-space-around-vs-space-evenly.png" alt="space-around vs space-evenly" width="500"></p>

<a id="align-items-row"></a>

### [Día 15: align-items [row]](#align-items-row)

Entonces justify-content controla cómo se distribuyen los elementos en el eje principal. ¿Qué pasa con su diseño en el eje transversal? No se preocupe, ahí es donde entran en juego los `align-items`. Recuerde que el eje transversal siempre es perpendicular al eje principal. Entonces, si el eje principal está sentado horizontalmente, donde la dirección de flexión es `row`. Entonces, el eje transversal está sentado verticalmente. ¿No te alegra que pasemos casi una semana en los fundamentos?, ese conocimiento se está aplicando ahora 🤓

<p><img src="../code-tidbits/15-align-items-row.png" alt="align-items row" width="500"></p>

```css
.padre {
  align-items: stretch /* por defecto */
             o flex-start
             o flex-end
             o center
             o baseline
}
```

<a id="baseline"></a>

### [Día 16: baseline](#baseline)

El valor baseline (línea base) es un poco complicado. Así que asegurémonos de entender qué es eso. Baseline tiene que ver con la tipografía o el texto. Es la línea imaginaria donde se encuentra el texto. Si tiene el mismo tamaño de fuente, realmente no ve una diferencia visual. Sin embargo, cuando tiene diferentes tamaños de fuente, el texto aparece por todas partes porque baseline está desactivada. La forma de garantizar una línea base uniforme donde todos los diferentes tamaños de texto se puedan apoyar es usar el valor de `baseline` 👍

<p><img src="../code-tidbits/16-baseline.png" alt="baseline" width="500"></p>

<a id="align-items-column"></a>

### [Día 17: align-items [column]](#align-items-column)

Ahora echemos un vistazo a cómo se alinean nuestros elementos flex si el eje transversal se asienta horizontalmente. En otras palabras, flex-direction es `column`.

<p><img src="../code-tidbits/17-align-items-column.png" alt="align-items column" width="500"></p>

```css
.padre {
  flex-direction: column;
  
  align-items: stretch /* por defecto */
             o flex-start
             o flex-end
             o center
             o baseline
}
```

<a id="align-content"></a>

### [Día 18: align-content](#align-content)

Recuerde que teníamos `flex-wrap` donde permitimos que los elementos flex se envuelvan en líneas separadas. Bueno, con `align-content` podemos controlar cómo se alinean esas filas de elementos en el eje transversal. Como esto es solo para elementos envueltos, esta propiedad no tendrá ningún efecto si solo tiene una línea única de elementos flex.

<p><img src="../code-tidbits/18-align-content.png" alt="align-content" width="500"></p>

```css
.padre {
  align-content: stretch /* por defecto */
                o flex-start
                o flex-end
                o center
                o space-between
                o space-around
}
```

**[⬆ volver arriba](#tabla-de-contenidos)**

## Propiedades del hijo

<a id="child-properties"></a>

### [Día 19: Propiedades del hijo](#child-properties)

¡Yay, lo hiciste! Lo hicimos usando las propiedades del padre. A continuación, profundizaremos en las propiedades del hijo. Toma un respiro hoy, mañana volveremos a toda velocidad 🏎

<p><img src="../code-tidbits/19-child-properties.png" alt="Child Properties" width="500"></p>

<a id="order"></a>

### [Día 20: order](#order)

De forma predeterminada, los elementos flex se muestran en el mismo orden en que aparecen en su código. Pero ¿y si quieres cambiar eso? ¡No hay problema! Use la propiedad `order` para cambiar el orden de sus elementos 🔢

<p><img src="../code-tidbits/20-order.png" alt="order" width="500"></p>

```css
.hijo {
  order: 0 /* por defecto */
       o <número>
}
```

<a id="flex-grow"></a>

### [Día 21: flex-grow](#flex-grow)

Mencioné al principio que Flexbox es ideal para un diseño receptivo. Aquí es donde brilla. La propiedad `flex-grow` que permite que nuestro elemento flex crezca si es necesario. Entonces, si hay espacio libre adicional en mi contenedor, puedo decirle a un elemento en particular que lo llene en función de alguna proporción. ¡Eso es bastante loco! Cuando estaba aprendiendo CSS, recuerdo que todo era bastante estático. Ahora con esta propiedad, es como si tuviera su propio cerebro y ajustará su tamaño según el contenedor. Eso es muy genial. No tengo que controlar el tamaño. Se ajustará en consecuencia. Este fue un gran golpe mental para mí 🤯

<p><img src="../code-tidbits/21-flex-grow.png" alt="flex-grow" width="500"></p>

```css
.hijo {
  flex-grow: 0 /* por defecto */
           o <número>
}
```

<a id="flex-grow-calculation"></a>

### [Día 22: flex-grow (cálculo)](#flex-grow-calculation)

Poder crecer y llenar el espacio libre es bastante genial. Debido a que no establecemos el ancho final de nuestro elemento flex, el tamaño en el que crece siempre me parece tan aleatorio. Así que echemos un vistazo a las matemáticas. Honestamente, no necesita saber esto para comprender Flexbox. El navegador se encarga de esto automáticamente por usted. Pero saber qué hay detrás de esta brujería podría desmitificar este proceso y ayudarlo a comprenderlo mejor. Es como una vez que conoces el truco de magia, ya no te engaña la magia 😉

<p><img src="../code-tidbits/22-flex-grow-calculation.png" alt="flex-grow calculation" width="500"></p>

<details>
  <summary><b>Click para expandir y ver el cálculo</b></summary><br>

Sé que puede ser bastante abrumador ver todos los números metidos en un tidbit (golosina). Así que veamos el cálculo 👍

Aquí están los `HTML` y` CSS` con los que estamos trabajando:

_HTML_

```html
<div class="padre">
  <div class="hijo verde"></div>
  <div class="hijo amarillo"></div>
  <div class="hijo azul"></div>
</div>
```

_CSS_

```css
.padre {
  width: 700px;
}
.hijo {
  width: 100px;
}
.verde {
  flex-grow: 1;
}
.amarillo {
  flex-grow: 0;
}
.azul {
  flex-grow: 3;
}
```

<br>

**Paso 1: Desglose de las variables**

Fórmula:

> **flex grow** = crecimiento flexible

```code
nuevo ancho = ( (flex grow / flex grow total ) x espacio libre) + ancho
```

Vamos a extraer las variables requeridas en la fórmula en esta práctica tabla que podemos completar a medida que avanzamos:

Variables       |     |
---             | --- |
flex grow       | *proporcionado por css*
flex grow total | *se necesita calcular*
espacio libre   | *se necesita calcular*
total           | *proporcionado por css*

<br>

**Paso 2: Completa lo que sabemos**

Del valor `CSS`, podemos concluir lo siguiente:

- Cada elemento hijo tiene un ancho `100`
- El elemento padre (contenedor) tiene un ancho de `700`
- Los hijos tienen un `flex-grow` de` 1`, `0`,` 3`

Actualicemos nuestra tabla con esta información:

<i> </i>        | Verde | Amarillo | Azul
---             | --- | --- | ---  |
flex grow       | 1   | 0   | 3
flex grow total |
espacio libre   |
ancho           | 100 | 100 | 100

<br>

**Paso 3: Calcular el "espacio libre"**

Fórmula:

```code
espacio libre = ancho del padre - ancho total de los hijos
```

Recuerda lo que sabemos:

- Cada elemento hijo tiene un ancho `100`
- El elemento padre (contenedor) tiene un ancho de `700`

Genial, podemos usar esa información para calcular el "ancho total de hijos":

```code
ancho total de los hijos = verde + amarillo + azul
                         = 100   + 100      + 100

=> 300
```

Ahora podemos calcular nuestro "espacio libre":

```code
espacio libre = ancho del padre - ancho total de los hijos
              = 700             -  300

=> 400
```

Actualicemos nuestra tabla y agreguemos esta información adicional:

<i> </i>        | Verde | Amarillo | Azul | Total
---             | --- | --- | ---  | ---  |
flex grow       | 1   | 0   | 3
flex grow total |
espacio libre   | -   | -   | -   | **400**
ancho           | 100 | 100 | 100

<br>

**Paso 4: Calcular el "flex grow total"**

Este es fácil, simplemente sumamos nuestro total de `flex-grow`:

```code
flex grow total = verde + amarillo + azul
                = 1     + 0        + 3

=> 4
```

Rellene nuestra tabla y ¡Voilà! Tenemos toda la información que necesitamos para el cálculo final 👍

<i> </i>      | Verde | Amarillo | Azul | Total
---           | ---   | ---      | ---  | --- |
flex grow     | 1     | 0        | 3    | **4**
espacio libre | -     | -        | -    | 400
ancho         | 100   | 100      | 100  |

<br>

**Paso final: Calcular el "nuevo ancho"**

Recuerda la fórmula:

```code
nuevo ancho = ( (flex grow / flex grow total) x espacio libre) + ancho
```

_a. Verde_

```code
nuevo ancho = ( (1/4 * 400) ) + 100

=> 200
```

_b. Amarillo_

```code
nuevo ancho = ( (0/4 * 400) ) + 100

=> 100
```

_c. Azul_

```code
nuevo ancho = ( (3/4 * 400) ) + 100

=> 400
```

¡Hecho! Hemos calculado con éxito el nuevo ancho 🥳

<i> </i>        | Verde   | Amarillo | Azul | Total
---             | ---     | ---      | ---  | --- |
ancho           | 200     | 100      | 400
flex grow       | 1       | 0        | 3    | 4
espacio libre   |         |          |      | 400
**nuevo ancho** | **200** | **100**  | **400**

<hr>

</details>

<a id="flex-shrink"></a>

### [Día 23: flex-shrink](#flex-shrink)

Entonces, `flex-grow` se expandirá para llenar el espacio extra si hay alguno. Lo contrario de eso es `flex-shrink`. Lo que sucede cuando te quedas sin espacio. Esta es la propiedad que controla cuanto se encogerán los elementos flex para ajustarse. Tenga en cuenta que cuanto mayor sea el número, más se reducirá 👍

<p><img src="../code-tidbits/23-flex-shrink.png" alt="flex-shrink" width="500"></p>

```css
.hijo {
  flex-shrink: 1 /* por defecto */
             o <número>
}
```

<a id="flex-shrink-calculation"></a>

### [Día 24: flex-shrink (cálculo)](#flex-shrink-calculation)

Este es otro conocimiento es opcional. Pero si eres como yo y tienes curiosidad por saber cómo calcula el navegador flex-shrink. Únete a mí en esta madriguera de conejo 🐰

La matemática detrás de `flex-shrink` es un poco más complicada que `flex-grow`. Debe tener en cuenta su proporción existente y reducirla de acuerdo con la cantidad de encogimiento. Por lo tanto, hay algunos cálculos más involucrados. De nuevo, si esto te está desanimando. Saltarlo. No necesita saber esto para comprender Flexbox. Afortunadamente, el navegador lo cuida por ti, qué maravilloso 😌

<p><img src="../code-tidbits/24-flex-shrink-calculation.png" alt="flex-shrink calculation" width="500"></p>

<details>
  <summary><b>Click para expandir y ver el cálculo</b></summary><br>

De hecho, el cálculo es un poco más complicado. Pero no te preocupes, vamos a analizarlo, lo revisamos paso a paso, tú lo tienes 💪

Aquí están los `HTML` y` CSS` con los que estamos trabajando:

_HTML_

```html
<div class="padre">
  <div class="verde"></div>
  <div class="amarillo"></div>
</div>
```

_CSS_

```css
.padre {
  width: 800px;
}
.verde {
  width: 300px;
  flex-shrink: 4;
}
.amarillo {
  width: 600px;
  flex-shrink: 6;
}
```

<br>

**Paso 1: Desglose de las variables**

Fórmula:

> **shrink space** = espacio de reducción
> **shrink ratio** = relación de reducción


```code
nuevo ancho = ancho - (shrink space x shrink ratio)
```

Vamos a extraer las variables requeridas en la fórmula a esta práctica tabla que podemos completar a medida que avanzamos:

Variables    |     |
---          | --- |
ancho        | *se necesita calcular*
shrink space | *se necesita calcular*
shrink ratio | *se necesita calcular*

<br>

**Paso 2: Completa lo que sabemos**

Del valor `CSS`, podemos concluir lo siguiente:

- El elemento padre (contenedor) tiene un ancho de `800`
- El elemento hijo verde tiene un ancho `300` y `flex-shrink` de `4`
- El elemento hijo amarillo tiene un ancho `600` y `flex-shrink` de `6`

Actualicemos nuestra tabla con esta información:

<i></i>     |  Verde | Anarillo |
---         | ---    | ---      |
flex shrink | 4      | 6
ancho       | 300    | 600

<br>

**Paso 3: Calcular "shrunk space" (espacio reducido)**

Formula:

```code
shrunk space = ancho total de los hijos - ancho del padre
```

Recuerda lo que sabemos:

- El elemento padre (contenedor) tiene un ancho de `800`
- Los elementos hijos tienen un ancho de `300` y `600`

Genial, podemos usar esa información para calcular el "ancho total de hijos":

```code
ancho total de los hijos = verde + amarillo
                         = 300   + 600

=> 900
```

Ahora podemos calcular nuestro "shrunk space":

```code
shrunk space = ancho total de los hijos - ancho del padre
             = 900                      -  800

=> 100
```

Actualicemos nuestra tabla y agreguemos la información adicional:

<i></i>          |  Verde | Amarillo | Total
---              | ---    | ---      | --- |
flex shrink      | 4      | 6
ancho            | 300    | 600
shrunk space     | -      | -        | **100**

<br>

**Paso 4: Calcular "shrink ratio" (relación de reducción)**

> **total shrink scaled width** = ancho total escalado de reducción

Formula:

```code
shrink ratio = (ancho x flex shrink) / total shrink scaled width
```

Noticia esta es una nueva variable, `total shrink scaled width`. Por lo tanto, primero debemos calcular eso para obtener nuestro shrink ratio.

<br>

**Paso 4-1: Calcular el  "total shrink scaled width" (ancho total escalado de reducción)**

Formula:

```code
total shrink scaled width = Σ(ancho x flex shrink)
```

"Σ" Sigma es un símbolo matemático que significa la suma de algo. Por lo tanto, debemos aplicar `ancho x flex shrink` para todos los elementos hijos.

_Verde_

```code
ancho x flex shrink = 300 x 4

=> 1200
```

_Amarillo_

```code
ancho x flex shrink = 600 x 6

=> 3600
```

_Finalmente_

```code
total shrink scaled width = 1200 + 3600

=> 4800
```

Agreguemos esta información a nuestra tabla:

<i></i>                            |  Verde | Amarillo | Total
---                                | ---    | ---      | --- |
flex shrink                        | 4      | 6
ancho                              | 300    | 600
shrunk space                       | -      | -        | 100
total shrink scaled width          | -      | -        | **4800**

<br>

**Paso 4-2: Volver a calcular "shrink ratio" (relación de reducción)**

Fantástico, ahora que conocemos el "total shrink scaled width", podemos regresar calculando el "shrink ratio". Recuerda la fórmula:

```code
shrink ratio = (ancho x flex shrink) / total shrink scaled width
```

_Verde_

```code
shrink ratio = (300 x 4) / 4800

=> 0.25
```

_Amarillo_

```code
shrink ratio = (600 x 6) / 4800

=> 0.75
```

Agreguemos esta información a nuestra tabla:

<i></i>      |  Verde   | Amarillo   | Total
---          | ---      | ---        | --- |
flex shrink  | 4        | 6
ancho        | 300      | 600
shrunk space | -        | -          | 100
shrink ratio | **0.25** | **0.75**

<br>

**Paso final: Calcular el "nuevo ancho"**

Recuerda la formula:

```code
nuevo ancho = ancho - (shrink space x shrink ratio)
```

_Verde_

```code
nuevo ancho = 300 - (100 x 0.25)

=> 275
```

_Amarillo_

```code
nuevo ancho = 600 - (100 x 0.75)

=> 525
```

¡Hecho! Hemos calculado con éxito el nuevo ancho 🥳

<i></i>         |  Verde   | Amarillo
---             | ---      | ---      |
ancho           | 300      | 600
shrunk space    | 4        | 6
shrink ratio    | 0.25     | 0.75
**nuevo ancho** | **275**  | **525**

<hr>
</details>

<a id="flex-basis"></a>

### [Día 25: flex-basis](#flex-basis)

Con la propiedad flex-grow y flex-shrink, sabemos que el tamaño de flex cambia. Con la propiedad `flex-basis`, aquí es donde establecemos su tamaño inicial. Puede considerar esta propiedad como el ancho de nuestros elementos flex. Entonces, su próxima pregunta podría ser cuál es la diferencia entre width y flex-basis. Por supuesto, aún puede usar el width y seguirá funcionando. La razón por la que funciona es porque si no configuró flex-basis, el width será predeterminado. Por lo tanto, su navegador siempre intentará encontrar el valor de `flex-basis` como indicador de tamaño. Y si no puede encontrarlo, entonces no tiene más remedio que ir con su propiedad de width. No hagas que el navegador haga un trabajo extra. Hágalo de la manera adecuada y use `flex-basis`.

Puede notar que hice referencia al ancho en mis fórmulas anteriores. Eso es porque no había cubierto flex-basis en ese punto. Entonces, si queremos ser **flex** correctos, reemplace donde mencioné el ancho con flex-basis 😝

<p><img src="../code-tidbits/25-flex-basis.png" alt="flex-basis" width="500"></p>

```css
.hijo {
  flex-basis: auto /* por defecto */
            o <ancho>
}
```

Los valores de ancho válidos son absolutos [`<longitud>`](https://developer.mozilla.org/es/docs/Web/CSS/length) y [`<porcentaje>`](https://developer.mozilla.org/es/docs/Web/CSS/porcentaje) . Puede ver algunos ejemplos y leer más en los documentos web de MDN:

- [`MDN: <longitud>`](https://developer.mozilla.org/es/docs/Web/CSS/length)
- [`MDN: <porcentaje>`](https://developer.mozilla.org/es/docs/Web/CSS/porcentaje)

<a id="flex-basis-vs-widths"></a>

### [Día 26: flex-basis vs width](#flex-basis-vs-widths)

Aquí puede ver muy claramente que cuando un elemento tiene flex-basis y un width. El navegador siempre usará el valor establecido con `flex-basis`. Nuevamente, otra razón para usar la forma adecuada 😉

Pero cuidado, si también configuras un `min-width` y un `max-width`. En esos casos, `flex-basis` perderá y no se utilizará como ancho.

<p><img src="../code-tidbits/26-flex-basis-vs-widths.png" alt="flex-basis vs widths" width="500"></p>

<a id="flex"></a>

### [Día 27: flex](#flex)

A veces, configurar `flex-grow`,` flex-shrink` y `flex-basis` por separado es agotador. Bueno, no te preocupes. Para los programadores perezosos, me refiero a los programadores eficientes 😜 Puede configurar los 3 con la abreviatura `flex`. La ventaja adicional de usar esta manera es que no tiene que establecer los 3 valores, puede omitir las propiedades que no le interesan y simplemente establecer la que es. Y para los que omitió, solo tomará el valor predeterminado. Impresionante 👍

<p><img src="../code-tidbits/27-flex.png" alt="flex" width="500"></p>

```css
.hijo {
  flex: 0 1 auto /* por defecto */
      o <flex-grow> <flex-shrink> <flex-basis>
      o <flex-grow>
      o <flex-basis>
      o <flex-grow> <flex-basis>
      o <flex-grow> <flex-shrink>
}
```

<a id="align-self"></a>

### [Día 28: align-self](#align-self)

Recuerda nuestra propiedad `align-items` donde podemos establecer el elemento flex a lo largo del eje transversal. Lo que ocurre con align-items es que obliga a TODOS los elementos flex a jugar con las reglas. Pero qué pasa si quieres que uno de ellos rompa la regla. No se preocupe, para los pensadores independientes, puede usar `align-self`. Esta propiedad acepta los mismos valores dados a `align-items`, por lo que puede separarse fácilmente del paquete 😎

<p><img src="../code-tidbits/28-align-self.png" alt="align-self" width="500"></p>

```css
.hijo-1 {
  align-self: stretch /* por defecto */
           o flex-start
           o flex-end
           o center
           o baseline
}
```

## Resumen

<a id="flexbox-properties"></a>

### [Día 29: Propiedades de Flexbox](#flexbox-properties)

¡¡¡HURRA!!! ¡Lo hiciste! ¡Aprendiste todas las propiedades de Flexbox! ¡Eres un ninja de Flexbox ahora! Cubrimos mucho en este corto período de tiempo. Regrese y vuelva a visitar los que aún no comprende. No solo lea mis lecciones de Flexbox. Consulte otros tutoriales de Flexbox. A veces, leer una perspectiva diferente ayudará a solidificar su conocimiento y llenar cualquier vacío. Recuerde que la mejor manera de mejorar es aplicarlo. Te di el conocimiento, ahora depende de TI aplicar y construir algo con él 💪

<p><img src="../code-tidbits/29-flexbox-properties.png" alt="Flexbox Properties" width="500"></p>

<a id="flexbox-cheatsheet"></a>

### [Día 30: Hoja de trucos para Flexbox](#flexbox-cheatsheet)

¡Tidbit (golosina) final! Déjame darte un dato más para el camino. Memorizar todas las propiedades disponibles no es fácil. Incluso después de crear todo este tutorial, todavía no tengo todas estas propiedades memorizadas. Ser un buen programador no se trata de cuánto memorizas, sino de resolver problemas. Y por eso es importante para un programador continuar siendo humilde y aprender. Se trata de expandir nuestro kit de herramientas para que cuando enfrentemos un problema, tengamos una variedad de herramientas que podemos seleccionar para solucionarlo 🧰

¡Felicitaciones por completar Flexbox30! Espero que hayas aprendido mucho y gracias por dejar que mis tidbits sean parte de tu viaje de programación 💛

<p><img src="../code-tidbits/30-flexbox-cheatsheet.png" alt="Flexbox Cheatsheet" width="500"></p>

**[⬆ volver arriba](#tabla-de-contenidos)**

<a id="auto-margins"></a>

### [Bonus: Alineación con márgenes automáticos](#auto-margins)

¡Contenido extra! Otra forma de alinear elementos hijos en Flexbox es usar márgenes automáticos. Aunque esta no es una propiedad de Flexbox, es importante tenerla en cuenta porque tiene una relación muy interesante con Flexbox. Consulte las notas de mi código si está interesado 👉 [Flexbox: Alineando con márgenes automáticos](/flexbox30-es/flexbox-aligning-with-auto-margins-es/README.md)

<p><img src="../code-tidbits/bonus-auto-margins.png" alt="Flexbox Cheatsheet" width="500"></p>

<a id="resources"></a>

## 📚 Recursos

**Aprendiendo Flexbox**

- [Documentos web de MDN: Flexbox](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout/Flexbox)
- [Documentos web de MDN: Conceptos básicos de Flexbox](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Flexible_Box_Layout/Conceptos_Basicos_de_Flexbox)
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Yoksel: Flex Cheatsheet](https://yoksel.github.io/flex-cheatsheet/)
- [JoniBologna.com: Flexbox Cheatsheet](http://jonibologna.com/flexbox-cheatsheet/)
- [Interneting is hard: Flexbox](https://internetingishard.com/html-and-css/flexbox/)

**Especificaciones oficiales**

- [W3C: Flexbox](https://www.w3.org/TR/css-flexbox-1/)

**Comunidades sugeridas**

- [Flexbox Zombies](https://flexboxzombies.com)
- [Flexbox Froggy](https://flexboxfroggy.com/)
- [Wes Bos: What the Flexbox?!](https://flexbox.io/)

<a id="say-hello"></a>

## 👋 Di hola

> ¡Comparto tidbits de JS, HTML, CSS cada semana!


Twitter: [@samantha_ming](https://twitter.com/samantha_ming)  
Instagram: [@samanthaming](https://www.instagram.com/SamanthaMing/)  
Facebook: [@hi.samanthaming](https://www.facebook.com/hi.samanthaming/)  
Medium: [@samanthaming](https://medium.com/@samanthaming)  
Dev: [@samanthaming](https://dev.to/samanthaming)  
Oficial: [samanthaming.com](https://www.samanthaming.com/)

<a id="download-and-share"></a>

## 💖 Descarga y Comparte

¡Absolutamente! Eres más que bienvenido a descargar y compartir mis tidbits de código. Si ha obtenido algún valor de mi contenido y desea ayudarme a llegar a más personas, ¡Comparta!

Una cosa que le pido amablemente es que no edite las imágenes ni recorte mi nombre. Por favor, deje las imágenes intactas. Gracias por elegir hacer lo correcto 😇

<a id="contribution"></a>

## 🌟 Contribución

¡Si! Cualquiera puede contribuir a la calidad de este contenido. No dude en enviar una solicitud de PR request para corregir errores tipográficos, correcciones ortográficas, mejoras de explicaciones, etc. Si desea ayudar a traducir el tutorial, ¡Eso es aún mejor! Espero al menos crear una versión china pronto 👩🏻‍🏫

**[⬆ volver arriba](#tabla-de-contenidos)**

<a id="license"></a>

## 👩🏻‍⚖️ Licencia

Gracias por querer compartir e incluir mi trabajo en su proyecto 😊 Si se pregunta cómo proporcionar las atribuciones. Simplemente significa que no edite las imágenes. Hay atribución incorporada automáticamente en ellos. ¡Fácil, fácil! Por lo tanto, no tiene que proporcionar una atribución adicional cuando comparte las imágenes ⭐️

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/80x15.png" /></a><br />Este trabajo tiene licencia bajo un <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>.

**[⬆ volver arriba](#tabla-de-contenidos)**
