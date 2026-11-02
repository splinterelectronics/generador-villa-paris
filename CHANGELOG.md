# Historial de cambios

Formato: [Versionado semántico](https://semver.org/lang/es/) — `MAYOR.MENOR.PARCHE`.
Para publicar una versión nueva: cambia `VERSION` en `index.html`, agrega una entrada aquí y crea la etiqueta (`git tag vX.Y.Z`) o un Release en GitHub.

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
