# Portafolio Interactivo

Práctica calificada 3 del curso de Hojas de Estilo en Cascada Avanzado. La idea era hacer una landing page para presentar mis proyectos, usando Bootstrap 5 para la estructura y CSS para los efectos y animaciones.

## ¿Cómo está organizado?

- `index.html`: la página.
- `styles.scss`: mis estilos escritos en SASS, para no repetir código (uso variables y mixins).
- `styles.css`: el CSS que sale de compilar el SCSS. Este es el que carga la página.

Si quieres recompilar el SCSS: `sass styles.scss styles.css`

## Lo que hice con Bootstrap

Con Bootstrap armé la barra de navegación, que en celular se convierte en el menú de hamburguesa. También usé su grid (`container`, `row`, `col-sm-12`, `col-md-4`...) para que el contenido se acomode solo según el tamaño de pantalla. El formulario de contacto tiene los campos de Nombre, Email y Mensaje con las clases `form-control` y `form-label`. Los botones Enviar y Limpiar usan `btn-primary` y `btn-secondary`, dentro de un `d-grid gap-2`.

## Transformaciones 2D

En la sección de proyectos hay tres tarjetas, y cada una hace algo distinto cuando pasas el mouse por encima:

- La primera **rota** un poco (`rotate`).
- La segunda **crece** (`scale`).
- La tercera **sube y se inclina** (`translate` y `skew`).

Todas tienen `transition` para que el cambio sea suave y no brusco.

## Transformaciones 3D

Hice dos efectos:

- **Tarjeta que gira:** al pasar el mouse da la vuelta y muestra su parte de atrás. El contenedor tiene `perspective` y la tarjeta usa `transform-style: preserve-3d` con `rotateX` y `rotateY`.
- **Cubo:** tiene seis caras y gira solo todo el tiempo. Si le pasas el mouse, se detiene.

## Animaciones

- **Título:** se escribe letra por letra, como una máquina de escribir (`@keyframes escribir`).
- **Círculo del inicio:** cambia de color y de tamaño sin parar (`@keyframes pulso`).
- **Loader:** al abrir la página sale un spinner girando, y hay otro pequeño dentro del botón Enviar.
- **Detalles extra:** el fondo del inicio se mueve, hay formas que flotan y las barras de habilidades se llenan al hacer scroll.

En las animaciones fui probando `animation-duration`, `animation-iteration-count`, `animation-timing-function`, `animation-delay` y `animation-direction` hasta que quedaron como quería.

## Diseño responsivo

Usé Flexbox y CSS Grid para ordenar el contenido, además de media queries para celulares y tablets. Probé la página con F12 en modo móvil y no hay desborde horizontal.

## Compatibilidad entre navegadores

Agregué prefijos como `-webkit-` en las transformaciones y animaciones. Las animaciones al hacer scroll solo se activan si el navegador las soporta (`@supports`), y si no, la página se ve normal. También respeté la opción de "reducir movimiento" para quien la tenga activada.