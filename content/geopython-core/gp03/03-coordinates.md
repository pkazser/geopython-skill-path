# 3. Συντεταγμένες και geometry

## Τι θα μάθεις

Θα μετατρέψεις τα δύο πεδία συντεταγμένων σε Points.

```python
import geopandas as gpd

gdf = gpd.GeoDataFrame(
    df,
    geometry=gpd.points_from_xy(df["longitude"], df["latitude"]),
    crs="EPSG:4326"
)
```

Η σειρά είναι πάντα `longitude` ως X και `latitude` ως Y.

## Πρώτος έλεγχος

```python
print(gdf.geometry.head())
print(gdf.geometry.geom_type.value_counts())
```

## Συνηθισμένο λάθος

Η αντίστροφη σειρά μπορεί να δημιουργήσει σημεία σε λάθος περιοχή χωρίς να εμφανιστεί error. Ο οπτικός έλεγχος είναι απαραίτητος.
