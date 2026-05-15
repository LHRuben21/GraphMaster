# GraphMaster
Aprendiendo a crear gráficos de alta calidad para artículos. Desde cero, con herramientas open source, paso a paso.

# 📊 Scientific Graphics for Research Publications

> Repositorio de aprendizaje progresivo en visualización científica de datos,

---

## 👤 Sobre este repositorio

Este repositorio documenta mi proceso de aprendizaje en la creación de gráficos
científicos de alta calidad para artículos de investigación. El objetivo es
desarrollar habilidades en visualización estadística y publicación académica
utilizando exclusivamente herramientas **open source**.

**Estado actual:** En progreso activo  
**Nivel en GraphMaster:** Nv. 4 → en avance  
**Módulos completados:** Módulo 1 — Fundamentos ✅

---

## 🗂️ Estructura del repositorio

```
scientific-graphics/
│
├── modulo_1_fundamentos/
│   ├── leccion_1_por_que_graficos/
│   │   └── notas.md
│   ├── leccion_2_herramientas/
│   │   ├── verificar_entorno.py          ← primer script ejecutado
│   │   └── notas.md
│   └── leccion_3_barras/
│       ├── grafico_barras.py
│       ├── figura1_barplot.pdf
│       └── notas.md
│
├── modulo_2_bioestadistica/
│   ├── leccion_4_boxplot/
│   ├── leccion_5_dispersion/
│   └── leccion_6_ic95/
│
├── modulo_3_graficos_avanzados/
│   ├── leccion_7_kaplan_meier/
│   └── leccion_8_heatmap/
│
├── modulo_4_publicacion/
│   ├── leccion_9_calidad_300dpi/
│   └── leccion_10_pipeline_completo/
│
├── figures/                   ← figuras finales exportadas en PDF/TIFF
├── data/                      ← datasets de ejemplo usados en los scripts
├── master_config.py           ← configuración global rcParams para todos los scripts
└── README.md
```

---

## 🛠️ Entorno de trabajo

| Herramienta | Versión | Uso |
|-------------|---------|-----|
| Python | 3.x (Anaconda) | Lenguaje principal |
| Matplotlib | 3.10.6 | Motor de gráficos base |
| Seaborn | 0.13.2 | Gráficos estadísticos elegantes |
| Pandas | 2.3.3 | Manejo de datos tabulares |
| NumPy | 2.3.5 | Cálculo numérico |
| SciPy | 1.16.3 | Pruebas estadísticas |
| Jupyter Notebook | — | Entorno de trabajo interactivo |
| Anaconda | — | Gestión del entorno |

> Las versiones corresponden a la instalación verificada el 14/05/2026
> en el terminal de Jupyter Notebook (ver imagen de verificación).

### Instalación del entorno

```bash
# Opción 1 — Instalar con pip (dentro de Jupyter terminal)
pip install matplotlib seaborn pandas numpy scipy

# Opción 2 — Todas las librerías ya vienen incluidas con Anaconda
# Descargar en: https://anaconda.com/download
```

### Verificar que todo funciona

```python
# verificar_entorno.py
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
import numpy as np

print("✓ Todo listo para hacer ciencia!")
```

---

## 📚 Contenido por módulo

### Módulo 1 — Fundamentos ✅

| Lección | Tema | Archivo | Estado |
|---------|------|---------|--------|
| 1 | ¿Por qué los gráficos importan en ciencia? | `notas.md` | ✅ |
| 2 | Herramientas: Python, Matplotlib, Seaborn | `verificar_entorno.py` | ✅ |
| 3 | Primer gráfico de barras científico | `grafico_barras.py` | ✅ |

### Módulo 2 — Bioestadística Visual ⌚

| Lección | Tema | Estado |
|---------|------|--------|
| 4 | Boxplot: la caja que lo dice todo | ✅ |
| 5 | Gráfico de dispersión y correlación | 🔒 |
| 6 | Barras de error e IC 95% | 🔒 |

### Módulo 3 — Gráficos Avanzados 🔒

| Lección | Tema | Estado |
|---------|------|--------|
| 7 | Curva de Kaplan-Meier (supervivencia) | 🔒 |
| 8 | Heatmap y matrices de correlación | 🔒 |

### Módulo 4 — Publicación 🔒

| Lección | Tema | Estado |
|---------|------|--------|
| 9 | Calidad para journals: 300 DPI, formatos | 🔒 |
| 10 | Flujo completo: del dato a la figura publicable | 🔒 |

---

## 🎯 Conceptos clave aprendidos

### Tipos de gráficos y cuándo usarlos

| Gráfico | Uso ideal | Herramienta |
|---------|-----------|-------------|
| Barras + error bars | Comparar grupos independientes | `plt.bar()` |
| Boxplot | Mostrar distribución completa | `sns.boxplot()` |
| Scatter + regresión | Correlación entre dos variables continuas | `sns.regplot()` |
| Kaplan-Meier | Análisis de supervivencia | `lifelines` |
| Heatmap | Matriz de correlaciones multivariable | `sns.heatmap()` |

### Barras de error — diferencias importantes

| Métrica | Fórmula | Cuándo usar |
|---------|---------|-------------|
| **SD** | √(Σ(x−x̄)²/n−1) | Describir variabilidad de la muestra |
| **SEM** | SD / √n | Precisión del estimador de la media |
| **IC 95%** | x̄ ± 1.96 × SEM | Inferencia — preferido por Nature, Cell, NEJM |

> ⚠️ Siempre especificar en la leyenda qué representan las barras de error.

---

## 📐 Estándares de publicación científica

```python
# master_config.py — configuración global para todos los scripts
import matplotlib as mpl

mpl.rcParams.update({
    'font.family':       'Arial',
    'font.size':         10,
    'axes.titlesize':    11,
    'axes.labelsize':    10,
    'xtick.labelsize':   9,
    'ytick.labelsize':   9,
    'legend.fontsize':   9,
    'axes.linewidth':    0.8,
    'lines.linewidth':   1.5,
    'figure.dpi':        150,   # pantalla
    'savefig.dpi':       300,   # guardado — mínimo para journals
    'savefig.format':    'pdf',
    'savefig.bbox':      'tight',
    'savefig.transparent': False,
})

# Tamaños estándar (en pulgadas)
UNA_COLUMNA  = (3.35, 2.50)   # 8.5 cm  — journals de 1 columna
DOS_COLUMNAS = (7.00, 4.50)   # 17.8 cm — journals de 2 columnas
PANORAMICO   = (7.00, 3.00)   # figura ancha y baja
```

### Lista de verificación antes de enviar a un journal

- [ ] Todos los ejes tienen etiqueta con unidades
- [ ] Título comienza con "Figura N."
- [ ] La leyenda especifica qué representan las barras de error
- [ ] Paleta de colores apta para daltónicos (colorblind-safe)
- [ ] La figura funciona en escala de grises
- [ ] Guardada en PDF o TIFF a ≥ 300 DPI
- [ ] Tamaño apropiado para el layout de la revista (1 o 2 columnas)
- [ ] Tipografía ≥ 8 pt en todo el gráfico
- [ ] El n por grupo está especificado en leyenda o título

---

## 🔬 Pipeline completo de trabajo

```
datos_brutos.csv
      │
      ▼
1. Cargar con pandas        → pd.read_csv('datos.csv')
      │
      ▼
2. Explorar y limpiar       → df.describe(), df.isnull().sum()
      │
      ▼
3. Análisis estadístico     → scipy.stats (t-test, ANOVA, Pearson...)
      │
      ▼
4. Crear figura             → matplotlib + seaborn + rcParams global
      │
      ▼
5. Checklist pre-publicación
      │
      ▼
6. Exportar                 → plt.savefig('FigN_descripcion.pdf', dpi=300)
```

---

## 📖 Recursos de referencia

- [Matplotlib documentation](https://matplotlib.org/stable/index.html)
- [Seaborn documentation](https://seaborn.pydata.org/)
- [Lifelines — análisis de supervivencia](https://lifelines.readthedocs.io/)
- [SciPy stats](https://docs.scipy.org/doc/scipy/reference/stats.html)
- [ColorBrewer — paletas científicas](https://colorbrewer2.org/)
- [Nature — guía de figuras](https://www.nature.com/documents/NRJs-guide-to-preparing-final-artwork.pdf)

---

## 📈 Progreso personal

```
Módulo 1  ████████████████████  100% ✅
Módulo 2  █████░░░░░░░░░░░░░░░    30% ⌚
Módulo 3  ░░░░░░░░░░░░░░░░░░░░    0% 🔒
Módulo 4  ░░░░░░░░░░░░░░░░░░░░    0% 🔒

XP total acumulado: 290 / 1440
```

*Este README se actualiza con cada módulo completado.*

---

## 📝 Notas personales

> Este repositorio es parte de mi plan de fortalecimiento como investigador
> con miras a la publicación de artículos en journals indexados. Los scripts
> aquí documentados son completamente reproducibles y están comentados línea
> por línea para facilitar la comprensión y reutilización.

---

*Última actualización: Mayo 2026*
