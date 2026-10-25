# Projects_Machine_Learning2026

Proyecto de aprendizaje automático que reúne dos ejercicios: carga y transformación de datos de arriendos en Colombia (EA1) y predicción de notas estudiantiles mediante regresión lineal (EA2).

## Integrantes

- **Natalia Jadith Castro Ospino**
- **Oscar Luis Marquez Arrieta**

## Ejercicios y fuentes de datos

### EA1: carga y transformación de datos

Carga desde Hugging Face el conjunto [Arriendo por estrato Colombia 2026](https://huggingface.co/datasets/aptologia/arriendo-por-estrato-colombia-2026). El notebook transforma los datos —incluye conversión de fechas, selección de columnas, filtro por estrato y cálculo del arriendo mediano en millones de pesos— y genera reportes TXT.

### EA2: regresión lineal

Utiliza el conjunto [Student Score Dataset](https://huggingface.co/datasets/MoazIrfan/student-score-dataset) para explorar si las notas de lectura y escritura permiten predecir la nota de matemáticas. El notebook entrena y evalúa una regresión lineal múltiple, presenta métricas y genera un reporte de resultados.

## Estructura del proyecto

```text
Projects_Machine_Learning2026/
├── .github/
│   └── workflows/
│       └── validar-proyecto.yml
├── src/
│   ├── clases/
│       ├── __init__.py
│       ├── hf_loader.py
│       ├── regresion_lineal.py
│       └── reportes.py
│   └── sincronizar/
│       ├── datos/
│       ├── reportes/
│       ├── EA1_Carga_de_Datos.ipynb
│       └── EA2_Regresion_lineal.ipynb
├── Sincronizar/
│   └── reportes/
├── requirements.txt
└── README.md
```

Los directorios `datos/` y `reportes/` contienen los archivos generados por los notebooks. EA1 también escribe su reporte transformado en `Sincronizar/reportes/`. Las rutas distinguen entre mayúsculas y minúsculas; por ejemplo, el nombre de EA2 es `EA2_Regresion_lineal.ipynb`.

## Tecnologías utilizadas

- **Python:** lenguaje de programación.
- **Pandas:** manipulación y transformación de datos.
- **Hugging Face Datasets:** acceso al conjunto de datos.
- **Jupyter Notebook:** ejecución y documentación del procesamiento.
- **scikit-learn:** entrenamiento y evaluación del modelo de regresión lineal.
- **Matplotlib:** visualización de datos.
- **Git y GitHub:** control de versiones y alojamiento del proyecto.
- **GitHub Actions:** ejecución automatizada de los notebooks.

## Componentes

- `HFDatasetLoader`: descarga un dataset de Hugging Face y opcionalmente lo guarda en un archivo.
- `Reportes`: crea reportes TXT con dimensiones, tipos de datos, valores nulos, duplicados y estadísticas descriptivas; también permite reportar resultados de regresión.
- `RegresionLineal`: prepara datos, entrena un modelo y permite generar predicciones y métricas.

## Instalación y configuración

### 1. Clonar el repositorio

```bash
git clone https://github.com/OscarLMAR/Projects_Machine_Learning2026_S10---EA1.git
cd Projects_Machine_Learning2026_S10---EA1
```

### 2. Crear el entorno virtual

```bash
python -m venv .venv
```

### 3. Activar el entorno virtual

En Linux, macOS o GitHub Codespaces:

```bash
source .venv/bin/activate
```

En Windows, utilizando PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 4. Actualizar pip e instalar las dependencias

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Iniciar Jupyter

Si el comando `jupyter notebook` no está disponible en el entorno, instala Jupyter:

```bash
python -m pip install jupyter
```

Inicia Jupyter desde la raíz del proyecto:

```bash
jupyter notebook
```

Abre y ejecuta los notebooks `src/sincronizar/EA1_Carga_de_Datos.ipynb` y `src/sincronizar/EA2_Regresion_lineal.ipynb`. También puedes abrirlos directamente en VS Code o GitHub Codespaces.

## Resultados

EA1 guarda los datasets y el reporte original en `src/sincronizar/datos/` y `src/sincronizar/reportes/`, y el reporte transformado en `Sincronizar/reportes/`. EA2 guarda sus datos y reporte en `src/sincronizar/datos/` y `src/sincronizar/reportes/`. Los notebooks muestran los resultados de cada ejecución; los valores pueden variar según los datos descargados y las transformaciones realizadas.

## Automatización con GitHub Actions

El workflow `.github/workflows/validar-proyecto.yml` se ejecuta al hacer `push` a `main`, al abrir o actualizar un *pull request* dirigido a `main`, y también se puede iniciar manualmente desde GitHub Actions. Utiliza Python 3.12, limpia los directorios de datos y reportes generados y ejecuta EA1 seguido de EA2.

En eventos distintos de *pull request*, si la ejecución produce cambios, GitHub Actions los confirma con la identidad `github-actions[bot]` y los sube a `main`. En los *pull requests* ejecuta los notebooks, pero no crea ni sube ese commit. El workflow requiere que el repositorio permita a GitHub Actions escribir contenido.

## Control de versiones

El proyecto utiliza Git para registrar los cambios realizados durante el desarrollo y GitHub para mantener el repositorio remoto actualizado.
