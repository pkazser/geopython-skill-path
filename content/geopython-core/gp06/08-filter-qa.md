# 8. QA μετά το filter

## Τι θα μάθεις

Θα αποδεικνύεις ότι ένα subset είναι αυτό που νομίζεις.

## Checklist

Για το `selected` έλεγξε rows, CRS, geometry types, missing values και κάθε predicate:

```python
assert selected["status"].eq("active").all()
assert selected["asset_type"].isin(["park", "school"]).all()
assert selected["score"].between(75, 100).all()
assert selected.geometry.notna().all()
```

## Γιατί έχει σημασία

Το πλήθος μόνο δεν αρκεί: δύο διαφορετικά φίλτρα μπορεί να επιστρέψουν ίδιο αριθμό features. Οι assertions ελέγχουν τη λογική και προστατεύουν το export.

## Άσκηση

Κατέγραψε counts πριν και μετά από κάθε συνθήκη. Αν το αποτέλεσμα γίνει μηδενικό, έλεγξε τιμές, τύπους και missing values πριν χαλαρώσεις το φίλτρο.

## Επόμενο βήμα

Στο Mini Challenge θα συνδυάσεις όλα τα είδη φίλτρων.
