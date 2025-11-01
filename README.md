# Dashboard Interactivo de Terremotos

Dashboard interactivo desarrollado con Python y Dash para el análisis y visualización de datos sísmicos a nivel mundial (1995-2023).

## Descripción

Este proyecto presenta un dashboard completo para explorar y analizar datos de terremotos mediante visualizaciones interactivas, análisis estadísticos y predicciones con Machine Learning. El dashboard está organizado en tres secciones principales: General, Espacio y Tiempo.

**Autor:** Juan Arturo Abaurrea Calafell  
**Proyecto:** Práctica final de Visualización Avanzada de Datos

## Características Principales

### 📊 Sección General
- **Gráfico de Violín**: Distribución de magnitud por alerta o tipo de magnitud
- **Gráfico de Densidad**: Distribución con histograma y KDE para magnitud o profundidad
- **Pie/Waffle Chart**: Distribución de alertas y tipos de cálculo de magnitud
- **Matriz de Correlación**: Heatmap de correlaciones entre variables numéricas
- **Diagrama de Venn**: Intersecciones entre terremotos con alerta roja, tsunamis y magnitud > 6
- **Bubble Plot**: Relaciones entre magnitud-profundidad-significancia
- **Radar Chart**: Perfil normalizado del top 10 de terremotos más significativos

### 🗺️ Sección Espacio
- **Distribución Geográfica**: Gráficos de barras y nubes de palabras por continente/país/ubicación
- **Treemap Jerárquico**: Visualización Continente → País → Ubicación
- **Mapa Folium Interactivo**: Con capas configurables (heatmap, clusters, círculos)
- **Gráfico de Latitud**: Distribución por hemisferios norte y sur
- **Globo 3D**: Representación tridimensional con profundidad de terremotos
- **Choropleth**: Mapas temáticos con métricas configurables
- **Box Plot**: Distribución de magnitud por continente
- **Predicción ML**: Modelo Random Forest para predecir ubicación y magnitud del próximo terremoto

### ⏱️ Sección Tiempo
- **Series Temporales**: Magnitud o cantidad con agregación configurable (hora/día/mes/año)
- **Animación Geográfica**: Evolución de terremotos por año en 2D o 3D
- **Stacked Area Chart**: Evolución de alertas por período
- **Calendar Heatmap**: Matriz año vs período con intensidad de eventos
- **Gráfico Polar/Circular**: Distribución radial por hora/día/mes

## Tecnologías Utilizadas

- **Procesamiento de Datos**: Pandas, NumPy, SciPy
- **Visualización Estática**: Matplotlib, PyWaffle, WordCloud, Matplotlib-Venn
- **Visualización Interactiva**: Plotly, Folium
- **Dashboard**: Dash, Dash Bootstrap Components
- **Machine Learning**: Scikit-learn
- **Procesamiento de Imágenes**: PIL (Python Imaging Library)

## Instalación

### Requisitos Previos
- Python 3.12.4

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/Jarturog/earthquakes-dashboard.git
cd earthquakes-dashboard
```

2. **(Opcional) Crear un entorno virtual**
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

3. **Instalar dependencias**
```bash
pip install -r requirements.txt
```

## Uso

### Ejecutar el Dashboard
```bash
jupyter notebook practica-final.ipynb
```

El dashboard estará disponible en: `http://localhost:8050`. También es accesible desde [earthquakes-dashboard.onrender.com](https://earthquakes-dashboard.onrender.com/).

### Configuración

Antes de ejecutar, asegúrate de que los siguientes archivos estén en el directorio correcto:
```
earthquakes-dashboard/
│
├── assets/
│   └── custom.css
├── dataset/
│   └── earthquake_1995-2023.csv
├── 2k_earth_specular_map.tif
└── practica-final.ipynb
```

## Dataset

### Fuente de Datos
- **Dataset**: [Earthquake Dataset en Kaggle](https://www.kaggle.com/datasets/warcoder/earthquake-dataset/data)
- **Período**: 1995-2023
- **Registros**: 1000 eventos sísmicos

### Variables del Dataset

| Variable | Descripción |
|----------|-------------|
| `title` | Nombre asignado al terremoto |
| `magnitude` | Magnitud del terremoto |
| `date_time` | Fecha y hora del evento |
| `cdi` | Intensidad máxima reportada |
| `mmi` | Intensidad instrumental máxima estimada |
| `alert` | Nivel de alerta (verde, amarillo, naranja, rojo) |
| `tsunami` | Indicador de tsunami (1 = sí, 0 = no) |
| `sig` | Significancia del evento |
| `depth` | Profundidad del epicentro |
| `latitude/longitude` | Coordenadas geográficas |
| `location` | Ubicación dentro del país |
| `continent` | Continente afectado |
| `country` | País afectado |

## Funcionalidades del Dashboard

### Filtros Interactivos
- **Continente**: Filtrar por continente específico
- **País**: Filtrar por país
- **Rango de Años**: Selector deslizante para período temporal
- **Solo Tsunamis**: Checkbox para filtrar eventos con tsunami
- **Alertas**: Selección múltiple de niveles de alerta

### KPIs Calculados
- Total de terremotos
- Magnitud media, mínima y máxima
- Número y porcentaje de tsunamis
- Alertas críticas vs moderadas
- Profundidad media y máxima
- Significancia media
- MMI y CDI promedio
- País y continente más afectados
- Tendencia temporal
