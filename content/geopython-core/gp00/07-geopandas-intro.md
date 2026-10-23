# 7. Πρώτη επαφή με GeoPandas

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_07_geopandas_intro_starter.ipynb)

## Τι θα μάθεις

- `GeoDataFrame`,
- geometry,
- CRS,
- `gpd.points_from_xy()`,
- geometry types,
- bounds,
- γρήγορη χαρτογράφηση,
- GeoJSON και GeoPackage.

## DataFrame → GeoDataFrame

```python
import pandas as pd

data = {
    "name": ["P1", "P2", "P3"],
    "longitude": [23.55, 23.56, 23.57],
    "latitude": [41.09, 41.10, 41.08]
}

df = pd.DataFrame(data)
```

Δημιουργία:

```python
import geopandas as gpd

gdf = gpd.GeoDataFrame(
    df,
    geometry=gpd.points_from_xy(
        df["longitude"],
        df["latitude"]
    ),
    crs="EPSG:4326"
)
```

## Έλεγχος

```python
print(gdf.crs)
print(len(gdf))
print(gdf.geometry.geom_type.value_counts())
print(gdf.total_bounds)
```

## QA γεωμετρίας

```python
print(gdf.geometry.isna().sum())
print(gdf.geometry.is_empty.sum())
```

## Γρήγορος χάρτης

```python
gdf.plot(figsize=(6, 6))
```

## Εξαγωγή

```python
gdf.to_file("points.geojson", driver="GeoJSON")
```

```python
gdf.to_file("points.gpkg", layer="points", driver="GPKG")
```

> 💡 **GeoTip**
>
> GeoDataFrame = DataFrame + geometry + CRS.

## Mini Challenge

Δημιούργησε 4 σημεία σε EPSG:4326, εμφάνισε CRS, rows, geometry types, bounds και plot.

## Επόμενο βήμα

**Errors, debugging και AI**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_07_geopandas_intro_solution.ipynb)
