# 4. `gpd.sjoin()` και join types

## Τι θα μάθεις

Θα χρησιμοποιείς `left` και `inner` ανάλογα με το αν θέλεις να κρατήσεις unmatched features.

## Παράδειγμα

```python
left = gpd.sjoin(services, districts, how="left", predicate="within")
inner = gpd.sjoin(services, districts, how="inner", predicate="within")
```

Το `left` κρατά και το S06 με null district. Το `inner` κρατά μόνο matches. Το `how` είναι απόφαση ανάλυσης, όχι διακοσμητική παράμετρος.

## Αναμενόμενο αποτέλεσμα

Το left αποτέλεσμα έχει τουλάχιστον έξι rows και ένα null match. Το inner έχει πέντε rows για το συγκεκριμένο dataset.

## QA

Σύγκρινε counts πριν/μετά, `isna().sum()` στα district fields και `geometry.geom_type`. Αν το inner έχει περισσότερα rows από τα services, ψάξε one-to-many σχέση.

## Επόμενο βήμα

Θα δεις γιατί ένα join μπορεί να αυξήσει τις γραμμές.
