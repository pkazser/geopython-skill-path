# 4. Schema και attributes

## Τι θα μάθεις

Θα καταλάβεις ποιες στήλες περιγράφουν κάθε feature.

```python
print(parks.dtypes)
print(parks.isna().sum())
print(parks["name"].unique())
```

Τα attributes απαντούν στο «τι είναι» κάθε γεωμετρία. Η geometry απαντά στο «πού είναι».

## Missing values

Μια κενή περιγραφή δεν σημαίνει απαραίτητα άκυρη geometry. Καταγράφουμε τα κενά και αποφασίζουμε ανάλογα με το ερώτημα.

## Checkpoint

Βρες ποια στήλη μπορεί να χρησιμοποιηθεί για φιλτράρισμα των πάρκων.

## Γιατί είναι χρήσιμο

Το schema απαντά τι μπορείς να ρωτήσεις. Στο `parks`, το `area_ha` επιτρέπει φίλτρο μεγέθους και το `name` βοηθά στην ερμηνεία του αποτελέσματος.

## Πρακτική εκτέλεση

```python
print(parks[["name", "area_ha"]])
print(parks["area_ha"].describe())
```

Θα δεις τρία πάρκα με διαφορετικό εμβαδόν. Δεν αρκεί να ξέρεις ότι υπάρχει στήλη· πρέπει να γνωρίζεις και τις μονάδες της.

## QA checkpoint

```python
assert parks["name"].notna().all()
assert parks["area_ha"].notna().all()
assert (parks["area_ha"] > 0).all()
```
