# 7. Validate — GeoPython QA checks

## Τι θα μάθεις

Το QA σημαίνει Quality Assurance. Δεν αρκεί ο κώδικας να εκτελείται· πρέπει και το αποτέλεσμα να είναι λογικό.

```python
assert len(gdf) > 0, "Δεν υπάρχουν εγγραφές"
assert gdf.geometry.notna().all(), "Υπάρχουν κενές γεωμετρίες"
assert gdf.geometry.geom_type.eq("Point").all(), "Δεν είναι όλα Points"
assert gdf.crs is not None, "Λείπει το CRS"
assert gdf["longitude"].between(-180, 180).all()
assert gdf["latitude"].between(-90, 90).all()
assert len(selected) > 0, "Το φίλτρο δεν επέστρεψε σημεία"
assert (selected["elevation_m"] > 70).all()
assert (selected["status"] == "checked").all()
```

Οι έλεγχοι δεν αποδεικνύουν ότι κάθε σημείο είναι σωστό, αλλά εντοπίζουν προφανή προβλήματα.
Αν ένα `assert` αποτύχει, σταματάμε και διορθώνουμε το πρόβλημα πριν το export.

## Checkpoint

Πρόσθεσε έναν έλεγχο που να επιβεβαιώνει ότι το `selected` δεν είναι κενό.

## Επόμενο βήμα

Μόνο αφού περάσουν οι έλεγχοι θα αποθηκεύσουμε το αποτέλεσμα.
