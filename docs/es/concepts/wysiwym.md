# Lo que ves es lo que quieres decir (LQVELQQD)

Markdown es un lenguaje basado en el paradigma llamado [Lo que ves es lo que quieres decir"](https://es.wikipedia.org/wiki/WYSIWYM) (LQVELQQD, de las mismas siglas de la frase en  inglés,  WYSIWYM). Este paradigma está relacionado con "Lo que ves es lo que obtienes" (LQVELQO, de la misma frase en inglés, WYSIWYG), que probablemente ya habrás escuchado. Procesadores de texto como Word o LibreOffice, por ejemplo, siguen este paradigma. LQVELQO quiere decir que lo que sea que  _ves_ en tu procesador de texto será lo que verás, independientemente de que guardes el documento como un  PDF o como HTML. El principio guía de LQVELQO, es que editar un documento debería coincidir precisamente con cualquier versión (exportada o impresa) del mismo.

En cambio, LQVELQQD, no hace tales afirmaciones. En lugar de "conseguir" lo que se ve, LQVELQQD se basa en la idea de que, lo que se ve, es lo que _se quiere decir_. En la práctica, esto implica que Markdown permite definir la _estructura_ de un texto (por ejemplo definir los encabezados, negritas, citas y enlaces) pero **no como se ve**. Los archivos Markdown necesitan ser procesados después para la publicación. En resumen: los archivos  Markdown son archivos "crudos"  que necesitan ser compilados en un formato final para su publicación.

El beneficio de este principio es que **separas el proceso de escritura del proceso de maquetación**. Esto tiene sentido increíblemente en muchas formas. Comparemos, por ejemplo, los archivos HTML con los PDF. Los archivos HTML están creados sobre el principio de maquetación flexible, esto es: puedes redimensionar la ventana de tu navegador y el archivo HTML se acomodará de tal manera que siempre se vea bien, no importa de qué forma lo redimensiones. Los archivos PDF, por otro lado, son lo opuesto a la flexibilidad: el formato PDF fue hecho para la impresión de documentos, así que esos documentos no pueden redimensionarse. Esto quiere decir que no se adaptará al tamaño de la ventana de tu lector de PDF. Sin embargo, esto permite que uses, por ejemplo, una maqueta de dos columnas o cabeceras y pies de página más fácilmente. La única cosa que ambos documentos tienen en común es la estructura: un encabezado en tu archivo PDF será también un encabezado en tu archivo HTML, incluso aunque se vea diferente. Y eso es lo que precisamente te permite hacer Markdown.

Algunos elementos, sin embargo, impactarán negativamente en tu flujo de trabajo. Por ejemplo, si quieres revisar rápidamente un párrafo que acabaste de escribir, los enlaces podrían perturbar la lectura, porque podría leerse como esto: `Una frase con [un enlace](https://docs.zettlr.com) en él`. Es más fácil leer frases como esta: `Una frase con _un enlace_ en él`. Es decir,  Zettlr prerenderizará estos enlaces para ti. Algo similar aplica a imágenes: Para nosotros, los humanos, es mucho más fácil ver la imagen que se supone debería estar allí, que sólo ver la ruta hacia ella.

Sin embargo, todos estos elementos renderizados _no_ coincidirán con tus archivos exportados. Simplemente están ahí para tu comodidad y las imágenes, por ejemplo, ofrecen algunas herramientas útiles para facilitar la edición, que no estarán en tus archivos exportados.

## Los saltos de línea no siembre son saltos de línea

Uno de los errores comunes, es el significado de los saltos de línea en Markdown y, tenemos que decir, que esta podría ser la idea más difícil de entender. 
Por defecto, Markdown **elimina los saltos de línea simples** y trata los **saltos de línea dobles como saltos de párrafo**. Sin embargo, se mantendrá un salto de línea. si está precedido por dos espacios o una barra invertida.

¿Por qué  Markdown hace esto? Hay múltiples razones. La mas importante puede ser histórica: Markdown fue desarrollado pensando en los editores de código, lo que implica que fue creado originalmente, para gente que está acostumbrada a hacer ajustes de línea cada 72-80 caracteres. Este principio es llamado  [Caracteres Por Línea (CPL)](https://en.wikipedia.org/wiki/Characters_per_line) y tiene raíces históricas.  Si bien para el texto este razonamiento puede ser contraintuitivo, Markdown ha mantenido esta idea, por lo que deberás prestar especial atención a los saltos de línea.

Algunas personas utilizan este comportamiento para su propio proceso de escritura: escriben una oración por línea para que les resulte más fácil recortar todas las oraciones aproximadamente a la misma longitud. Tomemos este ejemplo:

```md
Esta es una oración.
Esta es una segunda oración.
Esta oración es mucho más larga que las dos anteriores.
Una frase corta.

Este es el siguiente párrafo.
Otra oración en el segundo párrafo.
```

El ejemplo anterior resultará en dos párrafos, uno con cuatro oraciones y el otro con dos. Si deseas mantener ciertos saltos de línea, debes hacerlo explícito, ya sea terminando una línea con dos espacios o colocando una barra invertida al final de la línea:

```md
Esta oración estará en su propia línea.
Este también. \
Esto está en la tercera línea.
Esta oración vendrá directamente después de la tercera.
```

Ten en cuenta este comportamiento para saber cómo se verán tus documentos cuando los exporte, por ejemplo, a PDF o a Word.

> Si deseas obtener una descripción general de las ideas generales detrás de lo que puede y lo que no puedes hacer, consulta la [especificación CommonMark](https://spec.commonmark.org/), a la que Zettlr y el exportador subyacente, Pandoc, se adhieren.
