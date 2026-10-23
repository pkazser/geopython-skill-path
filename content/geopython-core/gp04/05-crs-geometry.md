# 5. CRS και γεωμετρίες

## Τι θα μάθεις

Θα ελέγξεις CRS, geometry types και valid geometries.

```python
assert parks.crs is not None
print(parks.geometry.geom_type.value_counts())
print("Empty:", parks.geometry.is_empty.sum())
print("Invalid:", (~parks.geometry.is_valid).sum())
```

Δεν υποθέτουμε ότι όλα τα layers ενός GeoPackage έχουν την ίδια geometry type. Τη διαβάζουμε και την επιβεβαιώνουμε.

## GeoTip

Το CRS του layer είναι κρίσιμο για τη σωστή θέση στον χάρτη και για μελλοντικές μετρήσεις.
