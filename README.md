# SpVAR Colombia – Streamlit App (Versión Ligera)

Dashboard interactivo de **Vectores Autorregresivos Espaciales (SpVAR)** para analizar la relación entre:

- Frontera Agrícola
- Infraestructura Vial
- Deforestación

a nivel de los departamentos de Colombia.

---

## Despliegue en Streamlit Cloud

1. Crea un repositorio en GitHub.
2. Sube estos tres archivos:
   - `app.py`
   - `requirements.txt`
   - `README.md` (este archivo)
3. Ve a [https://share.streamlit.io](https://share.streamlit.io)
4. Conecta el repositorio.
5. Configura:
   - **Main file path**: `app.py`
   - **Python version**: 3.10, 3.11 o 3.12
6. Haz clic en **Deploy**.

---

## Archivos del proyecto

| Archivo            | Descripción                                      |
|--------------------|--------------------------------------------------|
| `app.py`           | Aplicación principal (versión ligera y estable) |
| `requirements.txt` | Dependencias mínimas (sin geopandas)            |
| `README.md`        | Este archivo de documentación                   |

---

## Características del dashboard

- Simulador de choques (vial y agrícola) con respuesta de deforestación
- Ranking departamental interactivo
- Visualización 3D (VA Agrícola × Densidad Vial × Deforestación)
- Interfaz limpia y responsiva

---

## Notas importantes

- Esta versión **no utiliza** `geopandas`, `libpysal` ni `spreg` para garantizar compatibilidad total con Streamlit Cloud.
- Los datos mostrados son de **referencia** (orden de magnitud real según informes públicos de IDEAM, DANE y GFW).
- Para análisis científicos o de política pública, reemplace los datos por series oficiales.

### Fuentes oficiales recomendadas

- **Deforestación**: IDEAM – SMByC / Global Forest Watch / MapBiomas Colombia
- **Valor Agregado Agrícola**: DANE – Cuentas Nacionales Departamentales
- **Red vial**: INVIAS + DNP
- **Proxy satelital**: VIIRS nighttime lights o alertas FIRMS

---

## Licencia y uso

Código entregado con fines académicos, de investigación y de apoyo a la política pública.

**Última actualización**: Octubre 2026
