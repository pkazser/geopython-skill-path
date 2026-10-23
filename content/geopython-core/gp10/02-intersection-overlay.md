# 2. Intersection και overlay

## Τι θα μάθεις

Θα καταλάβεις το `gpd.overlay(..., how="intersection")`.

## Έννοια

Η intersection κρατά το κοινό τμήμα δύο layers. Το overlay δημιουργεί νέα γεωμετρία και συνδυάζει attributes από τα δύο inputs.

```python
overlap = gpd.overlay(landuse, protected, how="intersection")
```

Ένα residential ή green polygon κόβεται στη protected zone και το αποτέλεσμα έχει πεδία και από τα δύο layers.

## Πρακτική

Χρησιμοποίησε το clipped landuse ως πρώτο input και την protected zone ως δεύτερο. Δες τα νέα `landuse` και `zone_name` fields.

## QA

Έλεγξε ότι το output έχει μη κενές, valid Polygon/MultiPolygon geometries και θετικά areas. Το συνολικό area του overlap δεν μπορεί να ξεπερνά το clipped landuse area.

## Επόμενο βήμα

Θα συγκρίνεις καθαρά τα τρία εργαλεία.
