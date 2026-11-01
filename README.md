# Generador Villa Paris A — Calculadora de costo mensual

Aplicación web (un solo archivo `index.html`, sin servidor ni dependencias) que calcula cuánto le cuesta al condominio de la **Urb. Villa Paris A** el grupo electrógeno cada mes, y cuánto le toca pagar a cada unidad.

## Cómo calcula

```
Total del mes = ① Combustible + ② Mantenimiento prorrateado + ③ Costos fijos + ④ Fondo de reposición
```

| # | Componente | Fórmula |
|---|---|---|
| 1 | Combustible | (horas de cortes × L/h con carga + horas de prueba × L/h en vacío) × precio por litro + flete + aditivos |
| 2 | Mantenimiento | Por horas: costo × horas del mes ÷ intervalo en horas · Por calendario: costo ÷ intervalo en meses |
| 3 | Costos fijos | Suma de pagos mensuales (servicio técnico, operador, etc.) |
| 4 | Fondo de reposición | Valor de reposición ÷ (vida útil en años × 12) |

**Por unidad:** total ÷ número de unidades (partes iguales) o total × alícuota % (por alícuota). Con la tasa BCV se muestra también en bolívares.

Las horas de cada corte se calculan a partir de la hora de encendido y apagado (cubre los cortes que pasan de medianoche).

## Uso

1. Abre `index.html` en el navegador (o la versión publicada).
2. Llena los datos del generador, registra los cortes del mes y ajusta los precios.
3. **Guardar mes** lo deja en el historial del navegador; **Exportar / Importar** mueve los datos en un archivo `.json`.
4. **Imprimir / PDF** genera la hoja para la junta de condominio o la cartelera.

Los datos se guardan solo en el navegador del equipo que se usa (localStorage). Para pasarlos a otro equipo usa Exportar / Importar.

## Publicar

Al ser un sitio estático funciona directamente en **GitHub Pages** (Settings → Pages → rama `main`, carpeta raíz) o en **Cloudflare Pages**.

---
TUR1NG · LEVELMATIC
