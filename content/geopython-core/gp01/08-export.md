# 8. Export — Αποθήκευση αποτελέσματος

## Τι θα μάθεις

Θα αποθηκεύσεις το φιλτραρισμένο `GeoDataFrame` σε GeoJSON.

```python
from pathlib import Path

output_dir = Path("outputs/gp01")
output_dir.mkdir(parents=True, exist_ok=True)
output_path = output_dir / "high_checked_points.geojson"
selected.to_file(output_path, driver="GeoJSON")
```

Το GeoJSON είναι κατάλληλο για απλά γεωχωρικά δεδομένα και μπορεί να ανοιχτεί σε GIS λογισμικό.

## Έλεγχος του αρχείου

```python
exported = gpd.read_file(output_path)
print("Γραμμές:", len(exported))
print("CRS:", exported.crs)
```

Δεν θεωρούμε επιτυχημένο το export μόνο επειδή δεν εμφανίστηκε σφάλμα. Ξαναδιαβάζουμε το αρχείο και ελέγχουμε το αποτέλεσμα.

## Συνηθισμένο λάθος

Αν εξάγεις απλό `DataFrame` αντί για `GeoDataFrame`, δεν θα αποθηκευτεί σωστά η γεωμετρία. Έλεγξε ότι το `selected` έχει στήλη `geometry` και CRS.

## Επόμενο βήμα

Στο mini challenge θα επαναλάβεις τη ροή με διαφορετικό ερώτημα.
