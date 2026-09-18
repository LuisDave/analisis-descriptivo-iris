# Análisis descriptivo del dataset Iris

Guía para ejecutar y comprender un análisis exploratorio de la longitud del pétalo en el dataset Iris.

## Objetivo

El notebook estudia la variable `PetalLengthCm` para responder preguntas básicas de análisis de datos:

- ¿En qué intervalos se concentran las longitudes del pétalo?
- ¿Cuál es el valor típico y cuánto varían las observaciones?
- ¿Qué forma presenta la distribución?
- ¿Existen valores atípicos?

El resultado es un análisis reproducible con código, tablas, gráficas y explicaciones. Puede utilizarse como punto de partida para comparar especies o preparar modelos de clasificación.

## Contenido del proyecto

```text
.
├── data/
│   └── Iris.csv                         # Fuente de datos utilizada
├── notebooks/
│   └── analisis_descriptivo_iris.ipynb  # Notebook principal
└── README.md
```

El notebook utiliza únicamente `data/Iris.csv`.

## Requisitos

- Python 3.10 o superior.
- Jupyter Notebook o JupyterLab.
- Librerías: `pandas`, `numpy`, `matplotlib` y `scipy`.

## Instalación del entorno

Elige **una** de las siguientes opciones. Si usas Anaconda y tu terminal muestra `(base)`, se recomienda la primera.

### Opción A: Anaconda

En PowerShell, desde la carpeta del proyecto:

```powershell
conda install scipy pandas numpy matplotlib jupyter -y
```

### Opción B: entorno virtual de Python

En PowerShell, desde la carpeta del proyecto:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
py -m pip install pandas numpy matplotlib scipy jupyter
```

## Abrir y ejecutar el notebook

1. Abre PowerShell en la raíz del proyecto.
2. Si elegiste un entorno virtual, actívalo:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

3. Inicia Jupyter:

   ```powershell
   jupyter notebook notebooks\analisis_descriptivo_iris.ipynb
   ```

4. En el navegador, abre `analisis_descriptivo_iris.ipynb`.
5. Selecciona **Kernel → Restart Kernel** si habías instalado librerías recientemente.
6. Ejecuta todo con **Run All**.

Las tablas, gráficas e interpretaciones aparecerán debajo de las celdas correspondientes.

## Si aparece `ModuleNotFoundError: No module named 'scipy'`

El error indica que el kernel activo no tiene instalada la librería. No es un error del notebook ni de los datos.

La solución más directa es ejecutar esta celda nueva dentro del notebook:

```python
%pip install scipy pandas numpy matplotlib
```

Cuando finalice:

1. Selecciona **Kernel → Restart Kernel**.
2. Ejecuta de nuevo **Run All**.

También puedes instalar las librerías desde PowerShell con el comando de Anaconda o `pip` de la sección anterior. Es importante reiniciar Jupyter después de instalar paquetes para que el kernel detecte las nuevas versiones.

## Qué analiza el notebook

El flujo está dividido en secciones de análisis claramente separadas:

1. **Validación de datos**: carga el CSV, confirma que hay 150 registros y revisa valores faltantes.
2. **Distribución de frecuencias**: agrupa la longitud del pétalo en ocho intervalos de igual amplitud.
3. **Visualización de la distribución**: genera histograma, polígono de frecuencias y ojiva.
4. **Tendencia central**: calcula media aritmética, geométrica, armónica, recortada, moda y mediana.
5. **Dispersión**: calcula rango, desviación absoluta media, varianza, desviación estándar y coeficiente de variación.
6. **Forma**: analiza sesgo y curtosis.
7. **Posición y atípicos**: calcula cuartiles, deciles, límites de Tukey y muestra un diagrama de caja y bigote.

Cada resultado incluye interpretaciones escritas a partir de los valores calculados. No se limita a mostrar fórmulas o números aislados.

## Cómo leer los resultados

- La **tabla de frecuencias** indica cuántos registros pertenecen a cada intervalo de longitudes.
- El **histograma** muestra visualmente dónde se concentran las observaciones.
- El **polígono de frecuencias** facilita observar ascensos, descensos y posibles concentraciones.
- La **ojiva** muestra el número acumulado de observaciones hasta cada límite de clase.
- Las medidas de **tendencia central** describen un valor representativo de la variable.
- Las medidas de **dispersión** indican cuánto se alejan los valores entre sí y de su media.
- El **sesgo** y la **curtosis** ayudan a describir la asimetría y concentración de la distribución.
- El **diagrama de caja** resume los cuartiles y facilita identificar valores extremos.

## Comprobaciones útiles

Al ejecutar correctamente el notebook, deberías observar:

- 150 observaciones y cero valores faltantes en `PetalLengthCm`.
- Longitudes entre 1.0 y 6.9 cm.
- Ocho clases de frecuencia cuya suma es 150.
- Cuatro gráficas independientes: histograma, polígono de frecuencias, ojiva y diagrama de caja y bigote.
- Ningún valor atípico según la regla de Tukey aplicada en el análisis.

## Problemas frecuentes

| Situación | Solución |
|---|---|
| `ModuleNotFoundError` para `scipy`, `pandas`, `numpy` o `matplotlib` | Ejecuta `%pip install scipy pandas numpy matplotlib`, reinicia el kernel y vuelve a ejecutar el notebook. |
| No se encuentra `data/Iris.csv` | Abre Jupyter desde la raíz del proyecto y confirma que existe la carpeta `data/`. |
| Las gráficas no aparecen | Ejecuta **Run All** y espera a que finalice cada celda. Si instalaste librerías, reinicia el kernel antes. |
| El notebook sigue mostrando errores después de instalar paquetes | Cierra el notebook, detén Jupyter, vuelve a abrirlo y ejecuta **Run All**. |

## Próximos análisis posibles

Una vez ejecutado el flujo, el mismo proyecto puede extenderse para:

- Comparar `PetalLengthCm` entre las tres especies Iris.
- Analizar las demás mediciones físicas del dataset.
- Estudiar correlaciones entre variables.
- Preparar los datos para un modelo de clasificación de especies.
