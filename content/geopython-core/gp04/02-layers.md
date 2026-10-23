# 2. Layers και περιεχόμενο

## Τι θα μάθεις

Θα εντοπίσεις τα διαθέσιμα layers του GeoPackage.

```python
layers = gpd.list_layers(gpkg_path)
print(layers)
```

Η ακριβής εμφάνιση εξαρτάται από την έκδοση των βιβλιοθηκών, αλλά πρέπει να μπορείς να δεις τα ονόματα και τους βασικούς τύπους γεωμετρίας.

## Εναλλακτικός έλεγχος

Αν το `list_layers()` δεν είναι διαθέσιμο στο περιβάλλον, μπορείς να δοκιμάσεις τα γνωστά layer names με `gpd.read_file()` και να ελέγξεις το αποτέλεσμα.

## GeoTip

Το όνομα `parks` ή `water_points` είναι metadata του αρχείου. Δεν είναι όνομα στήλης.

## Γιατί είναι χρήσιμο

Η λίστα layers είναι ο κατάλογος περιεχομένων του GeoPackage. Χωρίς αυτήν κινδυνεύεις να διαβάσεις λάθος layer ή να υποθέσεις ότι το αρχείο περιέχει θεματικά δεδομένα που δεν υπάρχουν.

## Αναμενόμενο αποτέλεσμα

```python
layers = gpd.list_layers(gpkg_path)
print(layers["name"].tolist())
```

Πρέπει να δεις `parks` και `water_points`. Παρατήρησε ότι τα layers έχουν διαφορετικό geometry type: Polygon και Point.

## Πρόσεξε

Το `list_layers()` χρειάζεται σύγχρονο GeoPandas/pyogrio περιβάλλον. Αν αποτύχει, το πρόβλημα είναι δυνατότητα του περιβάλλοντος και όχι απαραίτητα του GeoPackage. Συνέχισε με γνωστά layer names και έλεγξε το αποτέλεσμα.

## QA checkpoint

```python
assert {"parks", "water_points"}.issubset(set(layers["name"]))
```
