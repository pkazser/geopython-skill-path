# 1. Τι είναι GeoPackage

## Τι θα μάθεις

Το GeoPackage είναι ένα ενιαίο αρχείο που μπορεί να περιέχει πολλά γεωχωρικά layers και attributes.

Σε αντίθεση με ένα απλό GeoJSON, δεν χρειάζεται ξεχωριστό αρχείο για κάθε layer.

```python
import geopandas as gpd

gpkg_path = "data/gp04/serres_assets.gpkg"
```

## Η σωστή ερώτηση

Δεν ξεκινάμε με `read_file()` σε layer που μαντέψαμε. Πρώτα ρωτάμε ποια layers υπάρχουν.

## Checkpoint

Ποια είναι η διαφορά ανάμεσα στο αρχείο GeoPackage και στο layer που θα διαβάσουμε από αυτό;
