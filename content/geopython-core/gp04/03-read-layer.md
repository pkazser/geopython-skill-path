# 3. Ανάγνωση layer

## Τι θα μάθεις

Θα διαβάσεις ένα συγκεκριμένο layer και θα πάρεις την πρώτη εικόνα του.

```python
parks = gpd.read_file(gpkg_path, layer="parks")
print(parks.head())
print("Rows:", len(parks))
```

Το αποτέλεσμα είναι `GeoDataFrame`. Από εδώ και πέρα εφαρμόζουμε τις ίδιες βασικές συνήθειες που έμαθες στο GP01.

## Πρώτος έλεγχος

```python
print(parks.columns)
print(parks.crs)
print(parks.geometry.geom_type.value_counts())
```

## Επόμενο βήμα

Θα εξετάσουμε το schema των attributes.
