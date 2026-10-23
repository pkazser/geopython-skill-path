# 8. Export — Αποθήκευση αποτελέσματος

## Τι θα μάθεις

Θα αποθηκεύσεις το φιλτραρισμένο `GeoDataFrame` σε GeoJSON.

## Τι πρόβλημα λύνουμε

Το αποτέλεσμα της μνήμης πρέπει να γίνει αρχείο που μπορεί να ανοίξει άλλος άνθρωπος ή άλλο GIS workflow. Το export είναι μέρος της ανάλυσης, όχι τελευταίο “save”.

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

Σύγκρινε `len(exported)` με `len(selected)`, έλεγξε ότι υπάρχει geometry και ότι τα βασικά attributes διατηρήθηκαν. Η επαναφόρτωση αποκαλύπτει προβλήματα path, driver ή schema που δεν φαίνονται κατά το write.

Δεν θεωρούμε επιτυχημένο το export μόνο επειδή δεν εμφανίστηκε σφάλμα. Ξαναδιαβάζουμε το αρχείο και ελέγχουμε το αποτέλεσμα.

## Συνηθισμένο λάθος

Αν εξάγεις απλό `DataFrame` αντί για `GeoDataFrame`, δεν θα αποθηκευτεί σωστά η γεωμετρία. Έλεγξε ότι το `selected` έχει στήλη `geometry` και CRS.

### Checkpoint

Άνοιξε το exported αρχείο με `gpd.read_file`, κάνε `assert len(exported) == len(selected)` και εμφάνισε `exported.total_bounds`. Αν ο αριθμός γραμμών άλλαξε, μην προχωρήσεις: έλεγξε το path και το format.

## Επόμενο βήμα

Στο mini challenge θα επαναλάβεις τη ροή με διαφορετικό ερώτημα.
