# SpVAR Colombia  
## Frontera Agrícola, Infraestructura Vial y Sostenibilidad Ambiental

**Modelo de Vectores Autorregresivos Espaciales (SpVAR)** aplicado a los 32 departamentos + Bogotá D.C. de Colombia.

---

### Descripción del proyecto

Este repositorio contiene un script profesional y modular en Python diseñado para Google Colab que implementa un sistema **Spatial VAR (SpVAR)** para analizar la interacción dinámica y geográfica entre:

- Deforestación
- Crecimiento del valor agregado agrícola
- Densidad de la red vial
- Proxy de presión antrópica (componente satelital)

El enfoque metodológico es estrictamente espacial (no un Panel VAR tradicional). Incluye:

- Selección empírica de la estructura espacial por ecuación (SAR / SEM / SAC / SDM) mediante pruebas de Multiplicadores de Lagrange (LM) y criterios de información.
- Evaluación y selección de la matriz de pesos espaciales **W** (contigüidad Queen vs Rook).
- Cálculo automático de efectos directos, indirectos (spillovers) y totales.
- Mapas coropléticos estéticos.
- Visualización 3D interactiva (Plotly).
- Aplicación web interactiva con **Gradio** para simular choques y observar la propagación espacial de la deforestación.

---

### Archivos incluidos

| Archivo | Descripción |
|---------|-------------|
| `spvar_colombia_completo.py` | Script completo listo para ejecutar en Google Colab o localmente |
| `spvar_colombia_completo.txt` | Versión en texto plano con instrucciones y resumen |
| `README_SpVAR_Colombia.md` | Este archivo de documentación |

---

### Requisitos

El script instala automáticamente las dependencias necesarias en Google Colab:

```bash
libpysal, geopandas, esda, spreg, matplotlib, seaborn, plotly, 
gradio, mapclassify, contextily, pandas, numpy, scipy, 
statsmodels, scikit-learn, openpyxl, xlrd, requests
```

---

### Cómo ejecutar

#### Opción 1 – Google Colab (recomendada)

1. Abra [Google Colab](https://colab.research.google.com).
2. Suba el archivo `spvar_colombia_completo.py` o copie su contenido en una celda.
3. Ejecute la celda (`Runtime → Run all` o `Shift + Enter`).
4. Espere a que se instalen las librerías y se generen los resultados.
5. La interfaz Gradio se abrirá automáticamente y generará un enlace público temporal.

#### Opción 2 – Local

```bash
pip install libpysal geopandas esda spreg matplotlib seaborn plotly gradio mapclassify contextily pandas numpy scipy statsmodels scikit-learn openpyxl xlrd requests
python spvar_colombia_completo.py
```

---

### Fuentes de datos oficiales recomendadas

| Variable | Fuente oficial |
|----------|----------------|
| Deforestación / pérdida de bosque | IDEAM – SMByC, Global Forest Watch, MapBiomas Colombia |
| Valor Agregado Agrícola | DANE – Cuentas Nacionales Departamentales (rama Agricultura, ganadería, caza, silvicultura y pesca) |
| Densidad / longitud de red vial | INVIAS + DNP |
| Proxy satelital (luces / fuego) | VIIRS nighttime lights (WorldPop / EOG) o alertas FIRMS |
| Límites departamentales | GeoJSON MGN-DANE 2018 (incluido en el script) |

> **Importante**: El panel de datos incluido en el script es de **referencia** (orden de magnitud y ranking correctos según informes públicos). Debe reemplazarse por series oficiales completas para cualquier análisis de producción o publicación científica.

---

### Estructura del script

1. Instalación automática de dependencias  
2. Carga del GeoJSON oficial de departamentos  
3. Construcción / carga del panel espacio-temporal  
4. Construcción y selección empírica de la matriz **W**  
5. Preparación de datos para el sistema SpVAR  
6. Selección de estructura espacial por ecuación (LM tests)  
7. Cálculo de impactos directos e indirectos (spillovers)  
8. Mapas coropléticos + visualización 3D  
9. Auditoría interna de robustez  
10. Aplicación interactiva Gradio  

---

### Canales de transmisión capturados por el SpVAR

El modelo permite ilustrar los cuatro canales fundamentales:

1. **Autodinámica espacial** (inercia interna y espacial de la variable)  
2. **Cruce local multivariante** (interacción dentro del mismo departamento)  
3. **Relación espacial directa contemporánea** (spillovers instantáneos vía W)  
4. **Relación espacial cruzada rezagada** (difusión espacio-temporal diferida)  

---

### Licencia y uso

Este código se entrega con fines académicos, de investigación y de política pública.  
Se recomienda citar las fuentes oficiales de datos (IDEAM, DANE, INVIAS, Global Forest Watch, etc.) en cualquier producto derivado.

---

**Última actualización**: Octubre 2026  
**Entorno objetivo**: Google Colab / Python 3.10+
