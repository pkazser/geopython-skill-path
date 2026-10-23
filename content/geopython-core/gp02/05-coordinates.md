# 5. Έλεγχος συντεταγμένων

## Τι θα μάθεις

Θα ελέγξεις ότι οι συντεταγμένες είναι αριθμητικές και βρίσκονται στα όρια του EPSG:4326.

```python
valid_coordinates = (
    clean["longitude"].between(-180, 180) &
    clean["latitude"].between(-90, 90)
)
clean = clean[valid_coordinates].copy()
```

Μια τιμή `999` μπορεί να είναι αριθμητικά έγκυρη ως Python number, αλλά όχι ως γεωγραφικό μήκος.

## Έλεγχος περιοχής

Για το συγκεκριμένο dataset μπορούμε να χρησιμοποιήσουμε και ένα πιο στενό, τοπικό εύρος για την περιοχή των Σερρών. Αυτό είναι κανόνας του dataset και όχι γενικός κανόνας για κάθε αρχείο.

```python
print(clean[["longitude", "latitude"]].describe())
```

## GeoTip

Οι συντεταγμένες δεν είναι ακόμη geometry. Είναι πεδία που θα χρησιμοποιήσουμε για τη δημιουργία geometry στο επόμενο βήμα.

## Γιατί είναι χρήσιμο

Μια συντεταγμένη εκτός ορίων μπορεί να τοποθετήσει ένα feature σε άλλη ήπειρο. Το πρόγραμμα μπορεί να εκτελεστεί κανονικά, αλλά το GIS αποτέλεσμα θα είναι λάθος.

## Πρακτική εκτέλεση

```python
print(clean[["observation_id", "longitude", "latitude"]])
valid = clean[clean["longitude"].between(-180, 180) & clean["latitude"].between(-90, 90)].copy()
print("Valid coordinates:", len(valid))
```

Η `O05` απορρίπτεται επειδή το longitude `999` δεν είναι γεωγραφικά δυνατό. Η `O06` έχει ήδη αποκλειστεί λόγω missing latitude.

## QA checkpoint

```python
assert valid["longitude"].between(-180, 180).all()
assert valid["latitude"].between(-90, 90).all()
```

Αυτός είναι γενικός έλεγχος ορίων. Για έργα συγκεκριμένης περιοχής μπορείς να προσθέσεις και έλεγχο αναμενόμενων τοπικών bounds.
