---
layout: article
title: "Simplificación de la finalización del pago con la API requestAutocomplete"
description: "Aunque <code>requestAutocomplete</code> se diseñó para ayudar a los usuarios a completar cualquier formulario, actualmente, su uso más común es el comercio electrónico, donde el abandono de los carritos de compra en la web móvil <a href='http://seewhy.com/97-shopping-cart-abandonment-rate-mobile-devices-concern-you/'>puede ser de hasta el 97 %</a>."
introduction: "Aunque <code>requestAutocomplete</code> se diseñó para ayudar a los usuarios a completar cualquier formulario, actualmente, su uso más común es el comercio electrónico, donde el abandono de los carritos de compra en la web móvil <a href='http://seewhy.com/97-shopping-cart-abandonment-rate-mobile-devices-concern-you/'>puede ser de hasta el 97 %</a>. Imagínese que el 97 % de las personas en un supermercado con el carrito lleno de artículos que desean voltearan el carrito y se fueran."
article:
  written_on: 2014-04-30
  updated_on: 2014-10-21
  order: 5
authors:
  - petelepage
priority: 0
collection: form-input
key-takeaways:
  use-request-auto-complete:
    - <code>requestAutocomplete</code>puede simplificar en gran medida el proceso de finalización del pago y mejorar la experiencia del usuario.
    - Si <code>requestAutocomplete</code> está disponible, oculte el formulario de finalización de pago y dirija a los usuarios directamente a la página de confirmación.
    - Asegúrese de que en los campos de entrada se incluya el atributo adecuado de compleción automática.
remember:
  use-placeholders:
    - Los marcadores de posición desaparecen tan pronto como el enfoque se centra en un elemento, por lo que no reemplazan a las etiquetas.  Se deben utilizar como ayuda para guiar a los usuarios sobre el formato y el contenido requeridos.
  recommend-input:
    - La compleción automática solo funciona cuando el método del formulario es la publicación.
  use-datalist:
    - Los valores de <code>datalist</code> se proporcionan como sugerencias, y los usuarios no están limitados a las sugerencias ofrecidas.
  provide-real-time-validation:
    - Incluso si se posee la validación de entrada de parte del cliente, siempre es importante validar los datos en el servidor para garantizar la coherencia y la seguridad de sus datos.
  show-all-errors:
    - Debe mostrarle al usuario todos los campos del formulario de una sola vez, en lugar de mostrárselos uno por uno.
  request-auto-complete-flow:
    - Si solicita algún tipo de información personal o datos de tarjetas de crédito, asegúrese de que el servicio de la página se ofrezca a través de SSL.  De lo contrario, en el cuadro de diálogo se le advertirá al usuario que su información puede no estar segura.
---
{% wrap content %}

<style>
  img, video, object {
    max-width: 100%;
  }

  img.center {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  table.inputtypes th:nth-of-type(2) {
    min-width: 270px;
  }

  table.tc-heavyright th:first-of-type {
    width: 30%;
  }
</style>

{% include modules/takeaway.liquid list=page.key-takeaways.use-request-auto-complete %}

En lugar de que el sitio dependa de un proveedor de pagos en particular,
`requestAutocomplete` solicita los detalles de pago (como nombre, dirección e información de la
tarjeta de crédito) desde el navegador, el cual los almacenan opcionalmente
 de manera similar a otros campos de autocompleción.

<div class="media media--video">
  <iframe src="https://www.youtube.com/embed/ljYeHwGgzQk?controls=2&modestbranding=1&showinfo=0&utm-source=crdev-wf" frameborder="0" allowfullscreen=""></iframe>
</div>

### Flujo de `requestAutocomplete`

En la experiencia ideal, se mostrará el cuadro de diálogo`requestAutocomplete` en lugar de cargar la
página en la que se muestra el formulario de finalización de pago. Si todo funciona correctamente, el usuario no debería ver
el formulario.  Puede agregar fácilmente `requestAutocomplete` a los formularios existentes
sin tener que cambiar los nombres de los campos.  Simplemente, agregue el atributo `autocomplete`
a cada elemento del formulario que posea el valor adecuado y agregue la función
`requestAutocomplete()` en el elemento del formulario. El navegador se encargará
del resto.

<img src="imgs/rac_flow.png" class="center" alt="Request autocomplete flow">

{% include_code _code/rac.html rac javascript %}

La función `requestAutocomplete` que aparece en el elemento del `form` le indica al
navegador que debe completar el formulario.  Como característica de seguridad, la función
se debe activar a través de un gesto del usuario, como un toque o un clic con el mouse. Luego, se muestra un cuadro de diálogo
en el que se solicita el permiso del usuario para completar los campos y para saber qué detalles
desea incluir en el formulario.

{% include_code _code/rac.html handlerac javascript %}

Cuando `requestAutocomplete` finalice, la función ejecutará el evento
`autocomplete` si se completó de forma exitosa, o bien `autocompleteerror` si no
pudo completar el formulario.  Si se completó exitosamente y el formulario
valida sus necesidades, simplemente envíelo y pase a la confirmación
final.

{% include modules/remember.liquid title="Remember" list=page.remember.request-auto-complete-flow %}

{% include modules/nextarticle.liquid %}

{% endwrap %}
