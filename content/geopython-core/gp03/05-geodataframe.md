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

## Γιατί είναι χρήσιμο

Το GeoDataFrame κρατά attribute table και geometry σε μία δομή. Αυτό επιτρέπει να φιλτράρεις με βάση το `condition` και ταυτόχρονα να χαρτογραφείς ακριβώς τις ίδιες γραμμές.

## Πρακτική εκτέλεση

```python
assets = gdf[["asset_id", "asset_type", "condition", "geometry"]].copy()
print(assets.shape)
print(assets.geometry.name)
```

Η geometry column δεν πρέπει να χαθεί όταν επιλέγεις στήλες. Αν την αφαιρέσεις, το αποτέλεσμα ξαναγίνεται απλό DataFrame.

## QA checkpoint

```python
assert len(assets) == len(gdf)
assert assets.geometry.name == "geometry"
assert assets.crs.to_epsg() == 4326
```
