# Análisis exploratorio: Iris y causas de falla

Este proyecto reúne dos análisis exploratorios independientes. Cada notebook tiene su propia fuente de datos, objetivo y visualizaciones.

## Objetivos

El proyecto permite responder dos grupos de preguntas:

- **Dataset Iris:** cómo se distribuye la longitud del pétalo, cuál es su valor típico, cuánto varía y si presenta valores atípicos.
- **Causas de falla:** qué problemas ocurren con mayor frecuencia y cuáles deben priorizarse para concentrar acciones de mejora.

## Estructura

```text
.
├── data/
│   ├── Iris.csv                         # Mediciones de flores Iris
│   └── causas_falla_frecuencias.csv     # Consolidado de 120 fallas operativas
├── notebooks/
│   ├── analisis_descriptivo_iris.ipynb  # Distribución de PetalLengthCm
│   └── analisis_causas_falla.ipynb      # Pareto y distribución de fallas
└── README.md
```

## Requisitos

- Python 3.10 o superior.
- Jupyter Notebook o JupyterLab.
- `pandas`, `numpy`, `matplotlib` y `scipy`.

## Instalación

Elige una opción. Si tu terminal muestra `(base)`, usa Anaconda.

### Con Anaconda

```powershell
conda install scipy pandas numpy matplotlib jupyter -y
```

### Con un entorno virtual de Python

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
py -m pip install pandas numpy matplotlib scipy jupyter
```

## Ejecutar los notebooks

1. Abre PowerShell en la raíz del proyecto.
2. Si creaste un entorno virtual, actívalo:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

3. Abre el análisis que necesitas:

   ```powershell
   jupyter notebook notebooks\analisis_descriptivo_iris.ipynb
   ```

   O el análisis de fallas:

   ```powershell
   jupyter notebook notebooks\analisis_causas_falla.ipynb
   ```

4. En Jupyter, ejecuta todas las celdas con **Run All**.

Si instalaste librerías recientemente, selecciona **Kernel → Restart Kernel** antes de ejecutar el notebook.

## Si aparece `ModuleNotFoundError`

El kernel activo no tiene instaladas las librerías requeridas. En una celda nueva del notebook ejecuta:

```python
%pip install scipy pandas numpy matplotlib
```

Después selecciona **Kernel → Restart Kernel** y ejecuta **Run All**.

## Notebook: análisis descriptivo de Iris

Archivo: `notebooks/analisis_descriptivo_iris.ipynb`  
Fuente: `data/Iris.csv`

Analiza exclusivamente `PetalLengthCm`, la longitud del pétalo en centímetros. Incluye:

1. Validación de 150 registros y valores faltantes.
2. Tabla de frecuencias con ocho intervalos.
3. Histograma, polígono de frecuencias y ojiva en figuras independientes.
4. Medidas de tendencia central: medias, moda y mediana.
5. Medidas de dispersión: rango, desviaciones, varianza y coeficiente de variación.
6. Sesgo y curtosis.
7. Cuartiles, deciles, detección de valores atípicos y diagrama de caja y bigote.

Al ejecutarlo deben aparecer 150 observaciones sin valores faltantes, longitudes entre 1.0 y 6.9 cm, ocho clases cuya frecuencia suma 150 y ningún valor atípico bajo la regla de Tukey.

## Notebook: análisis de causas de falla

Archivo: `notebooks/analisis_causas_falla.ipynb`  
Fuente: `data/causas_falla_frecuencias.csv`

Analiza 120 incidencias agrupadas en nueve causas. Incluye:

1. Tabla de frecuencias, porcentajes y porcentajes acumulados.
2. Diagrama de Pareto con una referencia visual al 80% acumulado.
3. Gráfico de pastel con la participación porcentual de cada causa.

El Pareto prioriza las causas de mayor impacto. Las cinco causas más frecuentes acumulan 80% de los registros, por lo que son el grupo principal para orientar acciones correctivas.

## Cómo interpretar las visualizaciones

- **Histograma:** concentra los registros de Iris por intervalos de longitud.
- **Polígono de frecuencias:** permite seguir las variaciones entre intervalos consecutivos.
- **Ojiva:** muestra cuántas observaciones se han acumulado hasta cada límite.
- **Caja y bigote:** resume cuartiles y ayuda a detectar extremos.
- **Pareto:** ordena las causas desde la más frecuente hasta la menos frecuente y revela prioridades.
- **Pastel:** comunica la proporción de cada causa dentro del total de fallas.

## Problemas frecuentes

| Situación | Solución |
|---|---|
| Falta `scipy`, `pandas`, `numpy` o `matplotlib` | Ejecuta `%pip install scipy pandas numpy matplotlib`, reinicia el kernel y vuelve a ejecutar. |
| No se encuentra un CSV | Abre Jupyter desde la raíz del proyecto y confirma que la carpeta `data/` existe. |
| No aparecen gráficas | Ejecuta **Run All** y espera a que finalice cada celda. |
| Persisten errores después de instalar paquetes | Cierra el notebook, detén Jupyter, vuelve a abrirlo y ejecuta **Run All**. |
