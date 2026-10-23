# 8. Export και οπτικός έλεγχος

## Τι θα μάθεις

Θα αποθηκεύεις το buffer αποτέλεσμα και θα επιβεβαιώνεις ότι έχει γεωγραφικό νόημα.

## Export

```python
school_buffers.to_file(
    "gp08_buffers.gpkg", layer="school_buffers", driver="GPKG"
)
```

Το GeoPackage κρατά CRS, attributes και geometry. Κράτησε τα IDs των αρχικών υπηρεσιών για να ξέρεις ποιο buffer αντιστοιχεί σε ποιο feature.

## Πριν το export

Έλεγξε rows, CRS EPSG:2100, Polygon/MultiPolygon geometry, μη κενές και valid geometries, bounds και θετικά areas. Έπειτα κάνε plot ή άνοιξε το layer σε GIS.

## Αναμενόμενο αποτέλεσμα

Τα buffers πρέπει να περιβάλλουν τις δύο σχολικές θέσεις και να έχουν ακτίνα 500 m στη σωστή κλίμακα. Αν καλύπτουν ολόκληρη την περιοχή, κάτι πήγε λάθος σε CRS ή units.

## Επόμενο βήμα

Στο Mini Challenge θα ολοκληρώσεις το workflow.
