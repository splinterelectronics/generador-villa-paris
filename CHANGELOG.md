# Historial de cambios

Formato: [Versionado semántico](https://semver.org/lang/es/) — `MAYOR.MENOR.PARCHE`.
Para cambiar de versión: actualiza `VERSION` en `index.html`, agrega una entrada aquí y crea la etiqueta (`git tag vX.Y.Z`).

## [1.1.0] — 2026-11-02
### Agregado
- Panel «¿Y si…?» con deslizador de horas y precio del diésel, tabla comparativa y costo por hora extra.
- Resumen que separa lo que se paga siempre de lo que depende del uso.
- Introducción, glosario, aviso de valores de ejemplo y barra de total fija en el celular.
- Tope en meses para el mantenimiento por horas («lo que ocurra primero»).
- Aviso de cortes con fecha de otro mes; versión visible y en los archivos exportados.
### Cambiado
- Valores de ejemplo y estimador de consumo más realistas (18 L/h con carga, 5 L/h en vacío).
- «Costo por hora» ahora es lo que cuesta cada hora extra encendido.
### Corregido
- Importar valida y pide confirmación; guardar mes avisa; tablas y tarjetas ya no se salen en el celular.
- Accesibilidad: etiquetas asociadas a campos y botones más grandes.

## [1.0.0] — Versión inicial
- Calculadora de costo mensual del grupo electrógeno con reparto por unidad, historial, exportar/importar e impresión.
