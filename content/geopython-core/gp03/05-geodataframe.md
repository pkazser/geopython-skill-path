# 5. Δημιουργία GeoDataFrame

## Τι θα μάθεις

Θα επιβεβαιώσεις ότι τα attributes και η geometry παραμένουν μαζί.

```python
print(gdf.shape)
print(gdf.columns)
print(gdf.crs)
print(gdf.geometry.geom_type.unique())
```

Το `GeoDataFrame` είναι DataFrame με μία ενεργή geometry column και CRS.

## Επιλογή πεδίων

```python
assets = gdf[["asset_id", "asset_type", "condition", "geometry"]].copy()
```

Κρατάμε μόνο τις στήλες που έχουν νόημα για το παραγόμενο GIS dataset.

## Checkpoint

Έλεγξε ότι ο αριθμός των rows παραμένει ίδιος μετά την επιλογή στηλών.
