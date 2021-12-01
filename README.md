# HTML, SVG, CSS y JavaScript

### Clase 3 → 25-11-2021

- - - - - - - 

#### Presentación

Ya reconocimos las diferencias entre [HTML](https://developer.mozilla.org/es/docs/Web/HTML), [SVG](https://developer.mozilla.org/es/docs/Web/SVG) y [CSS](https://developer.mozilla.org/es/docs/Web/CSS). Aprendimos que HTML describe, mediante elementos, a las páginas web. Su primo hermano, el SVG, hace lo mismo con los gráficos vectoriales. También aprendimos que CSS puede describir, mediante reglas, el aspecto de páginas web y gráficos vectoriales. 

Para avanzar rápido en la definición del aspecto de páginas web que [deben ser *responsivas*](https://youtu.be/iEB3oILm-qQ?t=1780), estamos aprovechando [el CSS de Bootstrap](https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.css).

En esta clase corresponde dar un paso que nos llevará desde lenguajes de descripción (HTML, SVG y CSS) a un lenguaje de programación que se ejecuta del lado del cliente: [JavaScript](https://jsparagatos.com/).

**JavaScript es un lenguaje de programación con el que las páginas web se hacen interactivas mediante el control de cada navegador web y su Modelo de Objetos de Documento ([DOM; Document Object Model](https://es.wikipedia.org/wiki/Document_Object_Model))**: Con JavaScript se controla, a través de pequeños programas (o *scripts*), la "comprensión de lectura" del navegador web. Por este motivo pueden haber diferencias entre **ver código fuente** e [**inspeccionar elementos**](https://support.hostinger.es/es/articles/2333029-como-inspeccionar-los-elementos-del-sitio-web).

- - - - - - - 

#### Exploración

Para encontrar las diferencias entre **ver código fuente** e **inspeccionar elementos** de la misma página, por favor copien el siguiente código y péguenlo en [Atom](https://atom.io/) o [Sublime Text](https://www.sublimetext.com/), para luego guardarlo con extensión `.html` y abrirlo en un navegador web (Chrome, Firefox o [Brave](https://brave.com/es/)):

```
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>¡JavaScript!</title>
  </head>
  <body>
    <button id="especial">Soy un botón</button>
    <script>
    	var x = document.getElementById("especial");
    	x.addEventListener("click", function(){
    	alert("¡Un mensaje de alerta!")
    	}, false);
    	x.insertAdjacentHTML("beforebegin", "Hola ");
    </script>
  </body>
</html>
```

Revisen el código fuente, y noten que no existe un "Hola" antes del `<button id="especial">Soy un botón</button>`, aun cuando pueden verlo gracias al control de la "comprensión de la lectura" del navegador web.

**Para hacer sentido de las instrucciones entre `<script></script>`, podemos poner atención a:**

- **La `x` después de `var`**. Allí creo (o declaro la existencia de) una variable de nombre `x`. Además de [`var`, podríamos usar `let` o `const`](https://medium.com/@tatymolys/var-let-y-const-donde-cuando-y-por-qu%C3%A9-d4a0ee66883b). Pueden imaginar que al usar `var`, `let`o `const` se crea una caja vacía, con su nombre marcado: En este caso, marcada con una `x`.

- **El signo `=` después de `x`**. Allí asigno a la variable recién creada un contenido. Pueden imaginar que estoy guardando algo en esa caja, y luego llamaré a ese algo por el nombre de la caja que lo contiene. Importante es agregar que en JavaScript lo igual es `==` y lo diferente es `!=`. Pero un único signo `=` es asignación de contenido (el algo de la caja marcada con `x` será tal cosa).

- **El `document.getElementById("especial")` después del signo `=`**. De lo ya intepretado por el navegador, quiero tomar aquello que tenga la identidad `especial`.

- **Las tres líneas que incluyen el `x.addEventListener("click", function(){}, false)`**. Le aviso al navegador que se disponga a escuchar el `click` de aquello que dejé guardado en `x`, y que corra una función si lo escucha.
 
- **El cierre con `x.insertAdjacentHTML("beforebegin", "Hola ")`**. Antes de terminar, vuelvo a tomar la caja marcada con la `x`, para que [se inserte](https://developer.mozilla.org/es/docs/Web/API/Element/insertAdjacentHTML), justo antes de su inicio, un "Hola".

La manera en que se escriban las instrucciones puede variar dependiendo de la lógica de la misma instrucción, [el estándar que se está respetando](https://www.w3schools.com/js/js_versions.asp), (1) las (malas)costumbres de quien progreme, (2) la biblioteca (*library*) de JavaScript en que nos apoyemos o (3) el marco de trabajo (*framework*) de JavaScript en que nos basemos.

1. Un ejemplo de (mala)costumbre: Usé `document.getElementById("especial")` cuando ya podría estar usando `document.querySelector("#especial")`. Si no tuviera esta (mala)costumbre, no me confundiría recordando o escribiendo `document.getElementById()`, `document.getElementsByClassName()` o `document.getElementsByTagName()`.

2. ¿Qué es una *library* de JavaScript? Es un montón de código preparado, que permite resolver cosas específicas, como [un gráfico](https://www.chartjs.org/), [un mapa](https://leafletjs.com/) o [una comparación de dos imágenes](https://image-compare-viewer.netlify.app/). Con una analogía cocinera: una biblioteca es como una sopa Maggi. 

3. ¿Qué es un *framework* de JavaScript? También es código preparado. La diferencia es que permite resolver cosas más grandes, como una aplicación web completa (ver [vue.js](https://v3.vuejs.org/) y [react.js](https://reactjs.org/)). Si insistimos en la analogía de la cocina, un framework ofrece una selección de ingredientes listos para hacer muchísimo más que sopa.

¿Por qué usar *libraries* o *frameworks* de JavaScript? Porque los requerimiento de interacción son cada vez más complejos, y las dinámicas del trabajo tienden al [Software funcionando tan rápido como sea posible](https://agilemanifesto.org/iso/es/manifesto.html). Es difícil que alguien programe desde cero.

¿Usaremos algún *framework* de JavaScript? No. 

¿Usaremos alguna *library* de JavaScript? Si. Hoy usaremos dos: La que ofrece [Bootstrap](https://getbootstrap.com/) e [Image Compare Viewer](https://image-compare-viewer.netlify.app/). 

La próxima clase podríamos revisar otra.

- - - - - - - 

#### Aplicación

Como en las clases pasadas, cuenta con algo preparado para profundizar de manera práctica: 

https://profesorfaco.github.io/infografia/clase-3/

En lo preparado encontrarán 5 *scripts* y 6 usos de JavaScript (se suma un uso por el [carousel de Bootstrap](https://getbootstrap.com/docs/5.1/components/carousel/#how-it-works))

Si están viendo en Chrome [la página web preparada para esta clase, que ya está hospeda en GitHub](https://profesorfaco.github.io/infografia/clase-3/), podrán ver un mensaje de advertencia en la consola de JavaScript. El motivo para ese mensaje tiene tres partes:

- Es el [audio](https://medium.com/@barzik/the-new-html5-video-audio-api-has-privacy-issues-on-desktop-chrome-5832c99c7659)

- Es [GitHub Pages](https://github.blog/changelog/2021-04-27-github-pages-permissions-policy-interest-cohort-header-added-to-all-pages-sites/)

- Es el [Federated Learning of Cohorts](https://amifloced.org/) 

Pero no es necesario alarmarse. 

- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/infografia/tree/main/clase-2) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/infografia/tree/main/clase-4) 
