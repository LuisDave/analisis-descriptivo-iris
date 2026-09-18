# Análisis descriptivo del dataset Iris

Práctica de análisis exploratorio para describir la distribución de la longitud del pétalo en el dataset Iris.

## Objetivo

Construir una lectura clara y reproducible de la variable `PetalLengthCm`: identificar dónde se concentran los datos, cuánto varían, qué forma tiene su distribución y si existen observaciones atípicas.

El notebook transforma datos crudos en tablas, visualizaciones y conclusiones interpretables. Es un punto de partida útil antes de aplicar segmentación, clasificación o cualquier otro modelo de datos.

## Contenido del proyecto

```text
.
├── data/
│   ├── Iris.csv                         # Fuente de datos utilizada
│   ├── archive.zip                      # Descarga original del dataset
│   └── database.sqlite                  # Base incluida en la descarga
└── notebooks/
    └── analisis_descriptivo_iris.ipynb
```

El análisis está en `notebooks/analisis_descriptivo_iris.ipynb`.

## Dataset y variable analizada

El archivo `Iris.csv` contiene 150 registros de flores Iris y cuatro mediciones físicas. Esta práctica se centra exclusivamente en `PetalLengthCm`, la longitud del pétalo expresada en centímetros.

El flujo verifica que la variable no tenga valores faltantes antes de ejecutar cualquier cálculo. No es necesario descargar ni mover archivos: el notebook toma los datos desde `data/Iris.csv`.

## Preparación del entorno

Se requiere Python 3.10 o superior y Jupyter. Si necesitas configurar el entorno desde cero, abre PowerShell en la raíz del proyecto y ejecuta:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
py -m pip install pandas numpy matplotlib scipy jupyter
```

## Ejecución

1. Abre PowerShell dentro de la carpeta del proyecto.
2. Activa el entorno virtual, si lo creaste:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

3. Abre el notebook:

   ```powershell
   jupyter notebook notebooks\analisis_descriptivo_iris.ipynb
   ```

4. En Jupyter, ejecuta todas las celdas con **Run All**.

Las tablas, gráficos e interpretaciones aparecerán debajo de las celdas correspondientes.

## Análisis incluido

El notebook desarrolla un flujo completo de estadística descriptiva:

1. Validación y vista inicial de los datos.
2. Tabla de distribución de frecuencias con ocho intervalos.
3. Histograma, polígono de frecuencias y ojiva.
4. Medidas de tendencia central: media aritmética, geométrica, armónica, recortada, moda y mediana.
5. Medidas de dispersión: rango, desviación absoluta media, varianza, desviación estándar y coeficiente de variación.
6. Forma de la distribución mediante sesgo y curtosis.
7. Cuartiles, deciles, regla de Tukey para valores atípicos y diagrama de caja y bigote.

Cada sección incluye interpretaciones basadas en los resultados calculados, no solo fórmulas o código.

## Cómo interpretar las salidas

- La tabla y el histograma muestran la frecuencia de cada intervalo de longitudes.
- El polígono permite seguir visualmente los cambios de frecuencia entre intervalos.
- La ojiva responde preguntas acumuladas, por ejemplo, cuántos registros no superan cierto valor.
- Las medidas centrales representan valores típicos; las medidas de dispersión muestran qué tanto se alejan los datos de esos valores.
- El sesgo y la curtosis describen la forma de la distribución.
- El diagrama de caja resume la zona central de los datos y facilita detectar valores extremos.

## Resultado

Al finalizar la ejecución tendrás un análisis reproducible de `PetalLengthCm`, con evidencia numérica, visual y explicativa. El notebook puede ampliarse después para comparar especies, analizar otras variables o preparar modelos de clasificación.
