# Projects_Machine_Learning2026

## S10 - EA1 - Carga y Creación de Dataset

El objetivo es cargar un conjunto de datos desde Hugging Face, procesarlo mediante Python y Pandas, aplicar transformaciones y generar un reporte en formato TXT.

## Integrantes

- **Natalia Jadith Castro Ospino**
- **Oscar Luis Marquez Arrieta**

## Objetivo del proyecto

Implementar un proceso para cargar y transformar datos usando Python, Jupyter Notebook y las librerías que necesitamos para el análisis de datos. Este proyecto incluirá clases que nos ayudarán a cargar el conjunto de datos y a generar reportes. Además, contaremos con un notebook que nos permitirá coordinar todo el procesamiento y documentar los resultados de manera clara.

## Fuente de datos

- **Plataforma:** Hugging Face
- **Dataset:** [Arriendo por estrato Colombia 2026](https://huggingface.co/datasets/aptologia/arriendo-por-estrato-colombia-2026)
- **Tema:** Información de arriendos por ciudad y estrato socioeconómico en Colombia.

## Estructura del proyecto

```text
Projects_Machine_Learning2026/
├── .github/
│   └── workflows/
│       └── validar-proyecto.yml
├── Sincronizar/
│   ├── datos/
│   │   └── arriendo-por-estrato-colombia-2026.csv
│   ├── reportes/
│   │   └── arriendo-por-estrato-colombia-2026.txt
│   └── EA1_Carga_de_Datos.ipynb
├── src/
│   └── clases/
│       ├── _init_.py
│       ├── hf_loader.py
│       └── reportes.py
├── requirements.txt
└── README.md
```

## Tecnologías utilizadas

- **Python:** lenguaje de programación.
- **Pandas:** manipulación y transformación de datos.
- **Hugging Face Datasets:** acceso al conjunto de datos.
- **Jupyter Notebook:** ejecución y documentación del procesamiento.
- **Git y GitHub:** control de versiones y alojamiento del proyecto.
- **GitHub Actions:** automatización de validaciones del proyecto.

## Funcionalidades implementadas

1. Carga del conjunto de datos desde Hugging Face.
2. Conversión de la columna de fecha al tipo de dato correspondiente.
3. Selección de columnas relevantes para el análisis.
4. Filtrado de registros correspondientes a los estratos 3 a 6.
5. Creación de una variable con el valor de la mediana del arriendo expresado en millones de pesos.
6. Generación y almacenamiento de un reporte TXT con información general, tipos de datos, valores nulos y estadísticas descriptivas del DataFrame transformado.

## Instalación y configuración

### 1. Clonar el repositorio

```bash
git clone https://github.com/Natalia890c/Projects_Machine_Learning2026.git
cd Projects_Machine_Learning2026
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

### 5. Ejecutar Jupyter Notebook

Si Jupyter no está incluido en las dependencias, se debe instalar con:

```bash
python -m pip install jupyter
```

Iniciar Jupyter Notebook desde la raíz del proyecto:

```bash
jupyter notebook
```

También es posible abrir directamente el archivo `Sincronizar/EA1_Carga_de_Datos.ipynb` desde el editor de GitHub Codespaces.

## Resultados

El procesamiento realizado en el notebook genera un DataFrame transformado y un reporte en formato TXT.

El resultado incluye **28 registros y 7 columnas**, después de aplicar las transformaciones. El reporte presenta los tipos de datos, los valores nulos, los registros duplicados y las estadísticas descriptivas de las variables numéricas.

## Automatización con GitHub Actions

El repositorio incluye `.github/workflows/validar-proyecto.yml`, diseñado para instalar las dependencias y validar la importación de las clases del proyecto cuando se realizan cambios en la rama principal o se crea una solicitud de integración (*pull request*).

## Control de versiones

El proyecto utiliza Git para registrar los cambios realizados durante el desarrollo y GitHub para mantener el repositorio remoto actualizado.
