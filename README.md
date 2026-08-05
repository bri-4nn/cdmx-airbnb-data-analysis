# 📊 Análisis de Mercado y Estrategia de Pricing de Airbnb en Ciudad de México

## 📌 Contexto del Proyecto
Este mini proyecto analiza la oferta y demanda de alojamientos vacacionales de Airbnb en la Ciudad de México utilizando datos públicos de **Inside Airbnb**. 

El objetivo es proveer recomendaciones estratégicas a propietarios e inversionistas del sector inmobiliario vacacional para maximizar sus ingresos (RevPAR) mediante la optimización de precios, requerimientos de estancias y la obtención del estatus de *Superhost*.

---

## 🛠️ Stack Tecnológico
* **Procesamiento y Limpieza de Datos:** Python (`pandas`, `numpy`)
* **Análisis Exploratorio (EDA):** Python (`seaborn`, `matplotlib`)
* **Visualización e Dashboard Interactivo:** Power BI (Modelado de Datos, DAX)
* **Control de Versiones y Documentación:** Git & GitHub

---

## 🎯 Preguntas de Negocio e Hipótesis Evaluadas

### 🔍 Preguntas de Negocio
1. **¿Cuál es el precio promedio por noche según la zona (alcaldía) y el tipo de alojamiento?**
2. **¿Existe una correlación entre las reseñas recientes y el precio establecido por noche?**
3. **¿Qué porcentaje de los anfitriones concentran más de 3 propiedades (hosts profesionales vs. particulares)?**

### 🧪 Hipótesis Planteadas
* **H1 (Estancias mínimas):** Los alojamientos con estancias mínimas largas (7+ noches) registran mayor disponibilidad anual (menor ocupación estimada) frente a los que permiten reservaciones de 1 a 2 noches.
* **H2 (Rating vs. Precio):** Una mayor puntuación de calificación (`review_scores_rating`) impacta positivamente el precio por noche, con un efecto más pronunciado en las 5 alcaldías con mayor oferta turística.
* **H3 (Estatus Superhost):** Los anfitriones reconocidos como *Superhosts* cobran una tarifa promedio más elevada que los anfitriones estándar sin sufrir una reducción en su ocupación anual.

---

## 💡 Hallazgos Clave (Data Storytelling)

### 1. Concentración del Mercado y Pricing por Zona
* Las alcaldías con mayor volumen de oferta y precio promedio son **Cuauhtémoc, Miguel Hidalgo y Coyoacán**, representando el **70.45%** de la oferta total analizada.
* El precio promedio por noche general en CDMX es de **$2,3200 MXN**, variando drásticamente desde **$1,320 MXN** para habitaciones privadas hasta **$2,750 MXN** para casas/departamentos enteros en zonas de alta gama (Polanco, Roma-Condesa).

### 2. Dominio de Anfitriones Profesionales (Pregunta 3)
* El **57.94%** de las propiedades pertenecen a anfitriones considerados **profesionales** (>3 propiedades), lo que refleja una creciente profesionalización en la gestión de inmuebles en la capital frente a un **42.06%** de anfitriones particulares.

### 3. Validación de Hipótesis
* **H1 (Rechazada):** Las propiedades con estancias mínimas de 1 a 2 noches mostraron una disponibilidad promedio de **263 días/año**, frente a **230 días/año** en aquellas que exigen 7+ noches. *Conclusión: Contrario a lo esperado, exigir estancias de 7+ noches incrementa la ocupación estimada en un 32.35%*
* **H2 (Rechazada):** En las zonas de alta demanda, la puntuación de calificación no determina la tarifa por noche (Correlación $r = 0.0788$). La variación en el precio entre alojamientos con calificaciones medias y altas es de apenas < 2%, demostrando que el precio depende principalmente del tipo de inmueble y la ubicación geográfica.
* **H3 (Aceptada):** Los *Superhosts* registran un precio promedio de **$2,516 MXN** vs **$2,146 MXN** de los anfitriones estándar, manteniendo una disponibilidad promedio idéntica (**263 días/año**), confirmando que la insignia genera un efecto de *premium pricing*.

---

## 📈 Dashboard en Power BI
*(Inserta aquí una captura de pantalla o GIF interactivo de tu Dashboard de Power BI)*

<img width="1469" height="807" alt="image" src="https://github.com/user-attachments/assets/0768793c-2f71-432d-b7eb-eeeba6dc39dd" />

### Características del Dashboard:
* **Filtros Dinámicos:** Selección interactiva por Alcaldía, Tipo de Alojamiento y Estatus de Superhost.
* **Mapa de Calor Geográfico:** Densidad de precios y volumen por ubicación exacta (Latitud/Longitud).
* **Métricas DAX Personalizadas:** Cálculo dinámico de Tarifa Promedio, Rating Medio, % de Superhosts y Total de Propiedades.

---

## 🚀 Recomendaciones de Negocio
1. **Flexibilidad en Estancias Mínimas:** Configurar requerimientos de estancia de máximo 2 noches para maximizar la ocupación durante fines de semana.
2. **Estrategia de Reputación:** Enfocar esfuerzos de servicio para alcanzar el estatus de *Superhost*, permitiendo capturar un margen adicional aproximado del **X%** en la tarifa nocturna.
3. **Estrategia para Inversionistas:** Priorizar la adquisición de departamentos enteros en alcaldías con alta densidad de demanda y balancear el pricing mediante modelos dinámicos orientados a volumen de reseñas.

---

## 🛠️ Estructura del Repositorio
```text
├── data/
│   ├── raw/                  # Dataset original de Inside Airbnb (listings.csv)
│   └── processed/            # Dataset limpio (cdmx_listings_powerbi.csv)
├── notebooks/
│   └── cdmx_airbnb_eda.ipynb # Código en Python (Limpieza, EDA y Pruebas Estatísticas)
├── reports/
│   └── dashboard_cdmx.pbix   # Archivo ejecutable de Power BI
└── README.md                 # Reporte ejecutivo del proyecto
