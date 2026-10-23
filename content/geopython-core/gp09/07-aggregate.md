# 7. Aggregation μετά το join

## Τι θα μάθεις

Θα μετατρέπεις πολλά joined rows σε συνοπτικό πίνακα ανά περιοχή.

## Κώδικας

```python
counts = (
    joined_inner.groupby(["district_id", "district_name"])
    .size().reset_index(name="service_count")
)
```

Το `groupby` μετρά υπηρεσίες ανά περιοχή. Το αποτέλεσμα δεν είναι πλέον point layer, αλλά πίνακας summary.

## Εφαρμογή

Υπολόγισε counts για τους πέντε matched services. Άθροισε `service_count` και επιβεβαίωσε ότι ισούται με το πλήθος των inner matches.

## QA / ερμηνεία

Μην ερμηνεύσεις missing district σαν μηδενικές υπηρεσίες. Είναι άγνωστη αντιστοίχιση και πρέπει να αναφερθεί ξεχωριστά.

## Επόμενο βήμα

Θα κάνεις τελικό QA, map και export.
