# 7. Filtering layer

## Τι θα μάθεις

Θα κρατήσεις μόνο τα features που απαντούν σε ένα συγκεκριμένο ερώτημα.

```python
large_parks = parks[parks["area_ha"] >= 5].copy()
```

Με το `.copy()` δημιουργούμε ανεξάρτητο αποτέλεσμα για επόμενες αλλαγές ή export.

## Έλεγχος φίλτρου

```python
print("Αρχικά:", len(parks))
print("Επιλεγμένα:", len(large_parks))
assert (large_parks["area_ha"] >= 5).all()
```

Πάντα ελέγχουμε ότι το φίλτρο δεν επέστρεψε απροσδόκητα μηδέν features.
