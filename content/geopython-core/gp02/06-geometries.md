# 6. Γεωμετρίες και invalid features

## Τι θα μάθεις

Θα δημιουργήσεις Points και θα ελέγξεις αν υπάρχουν κενές ή μη έγκυρες γεωμετρίες.

```python
import geopandas as gpd

gdf = gpd.GeoDataFrame(
    clean,
    geometry=gpd.points_from_xy(clean["longitude"], clean["latitude"]),
    crs="EPSG:4326"
)
```

Για Point geometries το `is_valid` είναι βασικός έλεγχος. Ελέγχουμε επίσης `isna()` και `is_empty`.

```python
print(gdf.geometry.isna().sum())
print(gdf.geometry.is_empty.sum())
print(gdf.geometry.is_valid.all())
```

Δεν «διορθώνουμε» invalid geometries χωρίς να ξέρουμε την αιτία. Στα σημεία, συνήθως επιστρέφουμε στις συντεταγμένες και διορθώνουμε την πηγή.

## Επόμενο βήμα

Θα ενώσουμε τα βήματα σε ένα καθαρό workflow.
