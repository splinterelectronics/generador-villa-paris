# ⚡ Tabla de Cálculo - VILLA PARÍS A
### Auditoría Operativa y Financiera de la Planta Eléctrica Cummins / Stamford (440 kVA)

Herramienta analítica e interactiva diseñada para la **Asociación Civil Villa París A** (Barquisimeto, Estado Lara, Venezuela). Permite modelar el costo real de operación horaria, mensual y anual de la planta eléctrica diésel comunitaria, integrando tanto el consumo de combustible como la amortización lineal obligatoria del mantenimiento mayor según el régimen de uso.

---

## 📋 Diagnóstico y Justificación Técnica

### 1. Régimen de Trabajo y Consumo
* **Equipo:** Generador Diésel Cummins / Stamford de 440 kVA (352 kW continuo con factor de potencia 0.8).
* **Demanda Residencial Típica:** Entre 150 kW y 250 kW (representa del 43% al 71% de la capacidad continua).
* **Demanda Promedio Verificada:** **200 kW** (~250 kVA / 57% de carga continua), equivalente a **4.0 kW por vivienda** en base a 50 casas.
* **Tasa de Consumo según Curva Cummins Oficial:**
  * **150 kW** (~43% carga · 3.0 kW/casa): **30 – 34 L/h** (promedio: 32 L/h · 4.69 kWh/L)
  * **176 kW** (50% carga nominal · 3.5 kW/casa): **38 – 41 L/h** (promedio: 39.5 L/h · 4.46 kWh/L)
  * **200 kW** (~57% carga · 4.0 kW/casa): **42 – 47 L/h** (promedio: **44.5 ≈ 45 L/h** · 4.49 kWh/L)
  * **250 kW** (~71% carga · 5.0 kW/casa): **54 – 60 L/h** (promedio: 57 L/h · 4.38 kWh/L)
  * **300 kW** (~85% carga · 6.0 kW/casa): **65 – 72 L/h** (promedio: 68.5 L/h · 4.38 kWh/L)
* **Precio Unitario del Diésel:** $1.00 / Litro.
* **Costo Horario de Combustible (a 200 kW / 45 L/h):**  
  45 L/h × $1.00/L = **$45.00 / hora**
* **Costo Energético Integral:**  
  ($45.00 combustible + $5.065 mantenimiento) ÷ 200 kWh = **$0.250 / kWh generado**

![Tabla de Consumo Cummins Stamford 440 kVA](docs/tabla-consumo-cummins-440kva.jpg)

### 2. Soporte Oficial del Mantenimiento Mayor (Factura RKN Supply FVSER/2026/00452)
El servicio mayor se ejecuta estrictamente cada **200 horas** de funcionamiento:

| Descripción del Insumo / Servicio | Cantidad | P. Unitario | Subtotal |
| :--- | :---: | :---: | :---: |
| Lubricante 15W40 Shell Rotella T-4 | 44 L | $12.50 | $550.00 |
| Filtro de Combustible FS1000 Fleetguard | 2 und | $58.00 | $116.00 |
| Filtro de Aceite LF9009 Fleetguard | 1 und | $94.00 | $94.00 |
| Filtro Trampa de Agua WF2076 Fleetguard | 1 und | $65.00 | $65.00 |
| Mano de obra especializada (>438 kVA) | 1 serv | $188.00 | $188.00 |
| **Total por ciclo de 200 horas** | — | — | **$1,013.00** |

![Factura RKN Supply FVSER/2026/00452](docs/factura-rkn-supply-2026.jpg)

### 3. Modelo Matemático de Reserva
Para evitar derrames presupuestarios o paradas forzadas por falta de repuestos, el fondo de mantenimiento se provisiona por hora consumida:

$$\text{Costo Horario de Mantenimiento} = \frac{\$1,013.00}{200\text{ h}} = \mathbf{\$5.065\text{ / hora}}$$

$$\text{Costo Integral por Hora de Generador} = \$45.00 + \$5.065 = \mathbf{\$50.065\text{ / hora}}$$

---

## 📊 Matriz Comparativa de Escenarios (Base: Mes de 30 días)

| Parámetro | 1. Recaudo Actual (4h s/mtto) | 2. Operación Sostenible (4h) | 3. Falla Habitual (6h) | 4. Falla Severa (7h) |
| :--- | :---: | :---: | :---: | :---: |
| **Horas de Uso Diario** | 4 h/día | 4 h/día | 6 h/día | 7 h/día |
| **Horas Acumuladas/Mes** | 120 h | 120 h | 180 h | 210 h |
| **Frecuencia de Mantenimiento** | Cada ~50 días | Cada ~50 días | Cada ~33 días | Cada ~28 días |
| **Gasto Mensual Gasoil** | $5,400.00 | $5,400.00 | $8,100.00 | $9,450.00 |
| **Reserva Mensual Mtto.** | $0.00 *(Descubierto)* | $607.80 | $911.70 | $1,063.65 |
| **Presupuesto Total Mensual** | **$5,400.00** | **$6,007.80** | **$9,011.70** | **$10,513.65** |
| **Déficit Mensual vs Recaudo Actual** | $0.00 | **-$607.80** | **-$3,611.70** | **-$5,113.65** |
| **Cuota Mensual (Base: 50 casas)** | $108.00 / casa | $120.16 / casa | $180.24 / casa | $210.28 / casa |
| **Cuota Mensual (Base: 60 casas)** | $90.00 / casa | $100.13 / casa | $150.20 / casa | $175.23 / casa |

---

## 🚀 Funcionalidades de la Aplicación

1. **Simulador Paramétrico en Tiempo Real:** Control deslizante de horas diarias (1 h a 24 h), precio del combustible, consumo (L/h), intervalo y costo del servicio.
2. **Distribución Automática de Alícuotas:** Cálculo dinámico de la cuota mensual sugerida por vivienda según el censo de casas activas.
3. **Módulo de Difusión para WhatsApp:** Genera un mensaje formateado con viñetas y totales listo para pegar en el grupo de copropietarios.
4. **Modo Imprimible / Exportable a PDF:** Formato limpio y libre de elementos interactivos para carteleras o actas de asamblea.
5. **Arquitectura Zero-Dependency:** Archivo único (`index.html`) con interfaz basada en Tailwind CSS y Font Awesome cargados vía CDN.

---

## 🌐 Enlaces en Vivo

* **Cloudflare:** [https://generador-villa-paris.celaya-ronalt.workers.dev](https://generador-villa-paris.celaya-ronalt.workers.dev)
* **GitHub Pages:** [https://splinterelectronics.github.io/generador-villa-paris/](https://splinterelectronics.github.io/generador-villa-paris/)

---

## 🛠️ Despliegue y Publicación

Para publicar esta herramienta en tu repositorio `generador-villa-paris`:

1. Clona el repositorio o accede a la raíz de tu proyecto:
   ```bash
   git clone https://github.com/splinterelectronics/generador-villa-paris.git
   cd generador-villa-paris
   ```
2. Asegúrate de que los archivos `index.html` y `README.md` estén en la carpeta principal.
3. Envía los cambios a la rama principal:
   ```bash
   git add index.html README.md docs/
   git commit -m "docs: balance auditado y aplicacion calculadora"
   git branch -M main
   git push -u origin main
   ```
4. En GitHub, ve a **Settings** > **Pages** > **Build and deployment**.
5. Selecciona la rama **`main`**, carpeta **`/ (root)`** y haz clic en **Save**.
6. En un minuto el aplicativo estará disponible en:
   ```text
   https://splinterelectronics.github.io/generador-villa-paris/
   ```
