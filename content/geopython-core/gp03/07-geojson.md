# 7. Export σε GeoJSON

## Τι θα μάθεις

Θα αποθηκεύσεις το GeoDataFrame σε ένα φορητό γεωχωρικό format.

```python
from pathlib import Path

output_dir = Path("outputs/gp03")
output_dir.mkdir(parents=True, exist_ok=True)
geojson_path = output_dir / "city_assets.geojson"
gdf.to_file(geojson_path, driver="GeoJSON")
```

## Επαλήθευση

```python
check = gpd.read_file(geojson_path)
assert len(check) == len(gdf)
assert check.crs is not None
print(check.head())
```

Το export δεν ολοκληρώνεται παιδαγωγικά αν δεν ξαναδιαβάσουμε το αρχείο.
