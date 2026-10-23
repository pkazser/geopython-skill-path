# 5. Συναρτήσεις και βιβλιοθήκες

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_05_functions_imports_starter.ipynb)

## Τι θα μάθεις

- `def`,
- παραμέτρους,
- `return`,
- `import`,
- aliases,
- `from ... import ...`,
- πρώτη χρήση Shapely.

## Πρώτη συνάρτηση

```python
def m2_to_ha(area_m2):
    return area_m2 / 10000
```

## Δύο παράμετροι

```python
def rectangle_area(width, height):
    return width * height
```

## Συνάρτηση με `if`

```python
def elevation_class(elevation):
    if elevation < 100:
        return "Low"
    elif elevation < 500:
        return "Medium"
    else:
        return "High"
```

## Βιβλιοθήκες

```python
import math
print(math.sqrt(25))
```

Alias:

```python
import pandas as pd
import geopandas as gpd
```

## Shapely Point

```python
from shapely.geometry import Point

point = Point(23.55, 41.09)
print(point)
```

> 💡 **GeoTip**
>
> `Point(x, y)` σημαίνει πρώτα X και μετά Y. Για geographic coordinates: `Point(longitude, latitude)`.

## Συνάρτηση που δημιουργεί Point

```python
from shapely.geometry import Point

def create_point(longitude, latitude):
    return Point(longitude, latitude)
```

## Mini Challenge

Δημιούργησε γεωμετρίες για πολλά stations με `for` και μία συνάρτηση `make_point(x, y)`.

## Επόμενο βήμα

**pandas**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_05_functions_imports_solution.ipynb)
