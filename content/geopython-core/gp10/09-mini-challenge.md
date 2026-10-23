# 9. Mini Challenge — Περιοχή μελέτης και προστασία

## Στόχος

Περιόρισε το land-use στη study area και υπολόγισε πόσα m² κάθε χρήση γης intersect την protected zone.

## Βήματα

1. Διάβασε τα τρία polygon layers και έλεγξε CRS/validity.
2. Μετέτρεψέ τα σε EPSG:2100.
3. Κάνε clip landuse με study area.
4. Κάνε overlay intersection με protected zone.
5. Πρόσθεσε area fields, κάνε map και export σε GeoPackage.

## Αναμενόμενο αποτέλεσμα

Το overlay έχει μόνο κοινές εκτάσεις, θετικά areas και attributes από landuse και protected layers.

## Ερμηνεία

Σύγκρινε το area πριν και μετά. Εξήγησε γιατί το clipped layer μπορεί να έχει περισσότερη συνολική έκταση από το overlay.

## Επόμενο βήμα

Ολοκλήρωσε το readiness checkpoint.
