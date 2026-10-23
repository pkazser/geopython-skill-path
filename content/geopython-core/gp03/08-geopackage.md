# 8. Export σε GeoPackage

## Τι θα μάθεις

Το GeoPackage μπορεί να φιλοξενήσει πολλά layers σε ένα αρχείο.

```python
gpkg_path = output_dir / "city_assets.gpkg"
gdf.to_file(gpkg_path, layer="assets", driver="GPKG")
```

## Έλεγχος layer

```python
check = gpd.read_file(gpkg_path, layer="assets")
print(check.crs)
print(check.geometry.geom_type.value_counts())
```

Το όνομα του layer είναι μέρος του workflow και πρέπει να είναι σαφές.

## GeoTip

Το GeoJSON είναι απλό για ανταλλαγή. Το GeoPackage είναι πρακτικό όταν θέλεις ένα αρχείο με περισσότερα layers και GIS metadata.
