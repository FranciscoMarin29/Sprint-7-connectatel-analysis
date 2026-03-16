# 📡 Análisis de Clientes ConnectaTel

Proyecto de análisis de datos para ConnectaTel, empresa de telecomunicaciones con operaciones en México y Colombia.

---

## 🎯 Objetivo

Explorar, limpiar y analizar el comportamiento de uso de los clientes (llamadas y mensajes) para identificar patrones de consumo, detectar comportamientos atípicos y crear segmentos accionables que permitan optimizar la oferta comercial.

---

## 📁 Datasets utilizados

| Archivo | Descripción | Registros |
|---|---|---|
| `plans.csv` | Catálogo de planes (precio, minutos, GB, costos extra) | 2 planes |
| `users_latam.csv` | Información de clientes (edad, ciudad, plan, churn) | 4,000 usuarios |
| `usage.csv` | Actividad real: llamadas y mensajes con duración y longitud | 39,972 eventos |

---

## 🔄 Etapas del análisis

1. **Carga y exploración** — Revisión de estructura, tipos de datos y primeras filas de cada dataset.
2. **Identificación de problemas de calidad** — Detección de nulos, sentinels y fechas fuera de rango.
3. **Limpieza básica** — Corrección de sentinel `-999` en edad, `'?'` en ciudad y fechas futuras (año 2026).
4. **Summary statistics** — Agregación de uso por usuario (mensajes, llamadas, minutos) y unión con perfil demográfico.
5. **Visualización y outliers** — Histogramas por plan y boxplots con método IQR para detectar valores extremos.
6. **Segmentación** — Clasificación de usuarios por nivel de uso (Bajo / Medio / Alto) y por edad (Joven / Adulto / Adulto Mayor).
7. **Insight ejecutivo** — Conclusiones y recomendaciones comerciales para stakeholders.

---

## 🛠️ Herramientas

- Python 3.9+
- pandas
- numpy
- seaborn
- matplotlib
- Jupyter Notebook / Google Colab

---

## ▶️ Cómo ejecutar el notebook

### Opción A — Google Colab (recomendado)

1. Abre [Google Colab](https://colab.research.google.com)
2. Ve a **File → Upload notebook** y sube el archivo `.ipynb`
3. Sube los tres archivos CSV a la carpeta `/datasets/` en Colab:
   - En el panel izquierdo, haz clic en el ícono de carpeta
   - Crea la carpeta `datasets` y sube `plans.csv`, `users_latam.csv` y `usage.csv`
4. Ejecuta todas las celdas con **Runtime → Run all**

### Opción B — Jupyter local

```bash
# Clona el repositorio
git clone https://github.com/TU_USUARIO/TU_REPO.git
cd TU_REPO

# Instala dependencias
pip install pandas numpy seaborn matplotlib jupyter

# Coloca los CSV en una carpeta llamada datasets/
# Luego abre el notebook
jupyter notebook S7_ConnectaTel_RESUELTO.ipynb
```

---

## 📊 Principales hallazgos

- El **73.6%** de los usuarios tiene un nivel de uso **medio** (5–9 llamadas y mensajes).
- El segmento de **alto uso** (7%) representa la mayor oportunidad de upsell hacia el plan Premium.
- Los **Adultos (30–59 años)** son el grupo dominante con el 50.5% de la base.
- Se detectaron outliers en minutos de llamada (máx. 155 min) que indican usuarios de consumo intensivo.

---

## 👤 Autor

Proyecto desarrollado como parte del Sprint 7 del programa de análisis de datos.
