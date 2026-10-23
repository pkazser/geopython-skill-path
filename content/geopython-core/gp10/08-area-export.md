# 8. Area, map και export

## Τι θα μάθεις

Θα μετατρέψεις την τομή σε μετρήσιμο και επαναχρησιμοποιήσιμο αποτέλεσμα.

## Κώδικας

```python
clipped["area_m2"] = clipped.geometry.area
overlay["area_m2"] = overlay.geometry.area
overlay.to_file("gp10_results.gpkg", layer="landuse_protected", driver="GPKG")
```

Το EPSG:2100 κάνει το area να έχει μονάδες m². Το GeoPackage μπορεί να περιέχει τόσο clipped όσο και overlay layer.

## QA πριν το export

Έλεγξε rows, CRS, geometry types, validity, empties, bounds και area sanity. Το `overlay.area_m2.sum()` πρέπει να είναι θετικό και μικρότερο ή ίσο από το clipped area.

## Αναμενόμενο αποτέλεσμα

Το output διατηρεί land-use και protected attributes και περιέχει μόνο κοινές γεωμετρίες. Επιβεβαίωσε το με map ή άνοιγμα σε GIS.

## Επόμενο βήμα

Στο Mini Challenge θα συνδυάσεις clip και overlay.
