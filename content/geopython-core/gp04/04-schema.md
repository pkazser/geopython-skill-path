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
