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

## Γιατί είναι χρήσιμο

Σε ένα πραγματικό GIS project μπορεί να έχεις πάρκα, δρόμους, υδάτινα σημεία και όρια στο ίδιο αρχείο. Το GeoPackage τα κρατά οργανωμένα ως layers, χωρίς να χρειάζεται να διαχειρίζεσαι πολλά shapefiles και βοηθητικά αρχεία.

## Πρακτική εκτέλεση

```python
from pathlib import Path

gpkg_path = Path("data/gp04/serres_assets.gpkg")
assert gpkg_path.exists()
```

Το path είναι αρχείο, όχι φάκελος. Το πρώτο QA check είναι να επιβεβαιώσουμε ότι υπάρχει πριν ζητήσουμε layer.

## Επόμενο βήμα

Θα ζητήσουμε από το αρχείο να μας δείξει τα διαθέσιμα layers.
