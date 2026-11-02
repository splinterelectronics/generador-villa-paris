# Historial de cambios

Formato: [Versionado semántico](https://semver.org/lang/es/) — `MAYOR.MENOR.PARCHE`.
Para publicar una versión nueva: cambia `VERSION` en `index.html`, agrega una entrada aquí y crea la etiqueta (`git tag vX.Y.Z`) o un Release en GitHub.

## [2.4.4] — 2026-11-02
### Corregido
- Tabla de escenarios: las etiquetas de color («Sin fondo mtto», «Falla severa», etc.) se partían a mitad de la píldora y salían cortadas; ahora van completas en su propia línea.
- Celular: la columna «Cuota/Casa» quedaba fuera de la pantalla; ahora la tabla muestra lo esencial (escenario, fondo de mantenimiento, total y cuota) y cabe completa.

## [2.4.3] — 2026-11-02
### Corregido
- PDF: la tabla de escenarios usa una línea por fila (etiquetas y cifras ya no se parten ni se pegan), las tarjetas pequeñas mantienen el mismo tamaño y los parámetros empiezan en hoja nueva en vez de dejar su título solo al final de la página anterior.

## [2.4.2] — 2026-11-02
### Corregido
- **PDF desde Safari:** salía descuadrado (tarjetas de cuota y total apretadas y cortadas, y la tabla de escenarios sin su última columna, «Cuota/Casa»). Safari decide el diseño con el ancho de la ventana pero imprime en el ancho del papel. Ahora el diseño de impresión es fijo y no depende del tamaño de pantalla.

## [2.4.1] — 2026-11-02
### Corregido
- Las vistas previas de Cloudflare para las ramas fallaban con «missing a `previews` block». Se agrega `wrangler.jsonc` (con `previews`) y `.assetsignore` (para no publicar README, CHANGELOG ni la configuración).

## [2.4.0] — 2026-11-02
### Corregido
- **PDF / impresión:** el número de la cuota (blanco sobre verde) salía casi invisible porque no se imprimían los colores de fondo; ahora se imprimen. Las tarjetas ya no se parten entre páginas, el encabezado es claro y sin barra pegajosa, y se oculta lo que no sirve en papel (barras deslizantes, botones, avisos).
- En el PDF los resultados van primero y los parámetros después. Al final se agrega la fecha de impresión y la versión.
### Eliminado
- Campo «Tasa BCV» y los montos en bolívares (también en el mensaje de WhatsApp).

## [2.3.0] — 2026-11-02
### Cambiado
- Los controles editables ahora tienen color: barras con relleno y perilla grande (verde para horas, azul para kW), casillas con borde y fondo de color (azul, ámbar, índigo, verde) que se resaltan al tocarlas, y botones de potencia en azul.
- Mensaje al inicio: «Lo que tiene color se puede cambiar».
- Las etiquetas de precio y número de casas ahora se actualizan con los datos.

## [2.2.0] — 2026-11-02
### Cambiado
- Tarjeta principal rediseñada: la cuota por casa ahora es un cuadro verde destacado, el total va a su lado con el mismo alto, y el espacio vacío se aprovecha.
- Barra nueva que muestra de qué se compone el total (combustible vs. reserva de mantenimiento), con sus montos.
- Títulos y números más grandes y mejor adaptados al celular.

## [2.1.0] — 2026-11-02
### Corregido
- **El cálculo se detenía con un error** al mover cualquier control: faltaban en el HTML los elementos `badgeCostPerHour` y `statDailyPerHome`. Las cifras de arriba, la tabla de escenarios, la alerta de déficit y el botón de WhatsApp no se actualizaban.
- Los textos con números fijos (75 casas, $0,98/L, $1.013, 225 kW, déficit de $3.200) ahora siguen a los datos que se escriben.
- El distintivo «Nube en Vivo» no era cierto (la página no usa la nube); ahora dice «Cálculo en vivo».
### Agregado
- Tasa BCV opcional: muestra la cuota y el total en bolívares (y en el mensaje de WhatsApp).
- Tarjeta «Cada hora encendida cuesta (gasoil + reserva)».
- Barra fija con la cuota por casa y el total en el celular.
- Versión visible, enlace a este historial y vista previa al compartir el enlace.

## [2.0.0] — Rediseño «Inventario EPC»
- Nueva interfaz para 75 viviendas (planta Cummins/Stamford 440 kVA), curva de consumo oficial, factura de mantenimiento RKN Supply, comparativa de escenarios, ayudas emergentes y mensaje para WhatsApp.

## [1.0.0] — Versión inicial
- Calculadora de costo mensual con reparto por unidad, historial, exportar/importar e impresión.
