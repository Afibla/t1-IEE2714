# IEE2714 — Fundamentos de Procesamiento de Imágenes

## Tarea 1 — Antonia Fibla

La tarea aborda tres problemas de procesamiento de imágenes:

1. Saturación selectiva de color.
2. Ecualización local y control de contraste.
3. Reescalado e interpolación bilineal.

---

## Estructura del repositorio

Cada pregunta se desarrolla en un notebook independiente. Cada notebook contiene tanto la implementación de los algoritmos como la experimentación, análisis y conclusiones correspondientes.

```text
.
├── README.md
│
├── P1_Saturacion.ipynb
├── P2_Ecualizacion.ipynb
├── P3_Reescalado.ipynb
│
├── data/
│   └── ...
│
└── results/
    └── ...
```

---

# Pregunta 1 — Saturación selectiva de color

El notebook `P1_Saturacion.ipynb` contiene la implementación y experimentación de la herramienta de saturación selectiva en función del tono.

La organización general del notebook es:

```text
P1_Saturacion.ipynb

├── Implementación
│   ├── Interpolación periódica de m(h)
│   ├── Función g_m
│   └── Modificación selectiva de saturación
│
└── Análisis y exploración
    ├── Configuraciones de puntos de control
    ├── Aplicación sobre distintas imágenes
    ├── Comparación HS vs L*C*h*
    ├── Exploración de parámetros
    ├── Caso de clipping
    └── Exploración adicional

```

Para las conversiones entre espacios de color se utilizan funciones de `scikit-image`, mientras que la interpolación y transformación selectiva son implementadas para esta tarea.

---

# Pregunta 2 — Ecualización local y control de contraste

El notebook `P2_Ecualizacion.ipynb` responde la pregunta 2.

La organización es:

```text
P2_Ecualizacion.ipynb

├── Implementación
│   ├── calcular_cdf()
│   ├── control_contraste()
|   └──ecualizacion_local()
│
└── Análisis y exploración
    ├── 1. Verificación de ecualización global
    ├── 2. Tamaño regiones y distancia entre regiones
    ├── 3. Número de bins
    ├── 4. Control de contraste
    ├── 5. Comparación con CLAHE
    ├── 6. Caso problemático
    ├── 7. Artefactos en fronteras
    └── 8. Exploración adicional

```

La implementación utiliza `NumPy` para las operaciones sobre arreglos y `Matplotlib` para la visualización. `scikit-image` se utiliza para lectura de imágenes y, cuando corresponde, para la referencia externa de CLAHE y otras funciones permitidas por el enunciado.


# Librerías utilizadas

La implementación se desarrolla en Python y utiliza principalmente las siguientes librerías:

* **NumPy**: operaciones numéricas y manipulación de arreglos.
* **Matplotlib**: visualización de imágenes, histogramas, curvas y resultados.
* **scikit-image**: lectura de imágenes, datos de prueba, conversiones entre espacios de color y funciones permitidas por el enunciado para comparación o referencia.

Las principales funciones utilizadas incluyen:

```python
import os
import numpy as np
import matplotlib.pyplot as plt

from skimage import io, data, color, exposure
from skimage.color import (
    rgb2lab,
    lab2rgb,
    rgb2hsv,
    hsv2rgb
)
```


---

# Requisitos

Se requiere:

* Python 3
* Jupyter Notebook o JupyterLab
* NumPy
* Matplotlib
* scikit-image

Las dependencias pueden instalarse mediante:

```bash
pip install numpy matplotlib scikit-image jupyter
```

---

# Ejecución

Cada pregunta puede ejecutarse de manera independiente desde su respectivo notebook.

Por ejemplo:

```bash
jupyter notebook
```

Luego se debe abrir el notebook correspondiente:

```text
P1_Saturacion.ipynb
P2_Ecualizacion.ipynb

```

Se recomienda ejecutar las celdas en orden desde el inicio del notebook para reproducir correctamente las implementaciones, experimentos, figuras y resultados.

---

# Datos e imágenes

Las imágenes utilizadas para los experimentos se encuentran en la carpeta `data/` o de scikit-image.

Los resultados y figuras generados durante la experimentación pueden almacenarse en la carpeta `results/`.

```text
data/
    imágenes utilizadas

results/
    figuras y resultados generados
```

---

# Reproducibilidad

Cada notebook contiene los parámetros utilizados en los experimentos y las figuras principales de cada análisis.

Para reproducir los resultados del informe:

1. Clonar o descargar este repositorio.
2. Instalar las dependencias indicadas.
3. Abrir el notebook correspondiente.
4. Ejecutar las celdas en orden.
5. Verificar los parámetros indicados en cada experimento.

Las figuras y comparaciones presentadas en el informe se generan a partir de los experimentos contenidos en estos notebooks.
