# 3. Τύποι δεδομένων

## Τι θα μάθεις

Οι αριθμητικές στήλες πρέπει να είναι αριθμοί. Αν μια longitude είναι κείμενο, οι συγκρίσεις και οι γεωμετρίες μπορεί να αποτύχουν.

```python
df.dtypes
```

## Μετατροπή με έλεγχο

```python
for column in ["longitude", "latitude", "elevation_m"]:
    df[column] = pd.to_numeric(df[column], errors="coerce")
```

Το `errors="coerce"` μετατρέπει μη αναγνώσιμες τιμές σε `NaN`. Αυτό είναι χρήσιμο μόνο αν στη συνέχεια μετρήσουμε και χειριστούμε τα νέα κενά.

```python
df.isna().sum()
```

## Συνηθισμένο λάθος

Το `"100"` δεν είναι ίδιο με το `100`. Το πρώτο είναι `str`, το δεύτερο `int`.

## Checkpoint

Έλεγξε ότι `longitude`, `latitude` και `elevation_m` είναι αριθμητικές στήλες πριν συνεχίσεις.

## Γιατί είναι χρήσιμο

Οι τύποι επηρεάζουν άμεσα τις συγκρίσεις. Η σύγκριση κειμένου με αριθμό μπορεί να αποτύχει ή να δώσει λάθος λογική. Το ίδιο πρόβλημα θα μεταφερθεί στη δημιουργία geometry και στο filtering.

## Πρακτική εκτέλεση

```python
before = df["elevation_m"].dtype
df["elevation_m"] = pd.to_numeric(df["elevation_m"], errors="coerce")
after = df["elevation_m"].dtype
print("Πριν:", before, "Μετά:", after)
```

Η τιμή `not_available` γίνεται `NaN`. Δεν τη μετατρέψαμε αυθαίρετα σε μηδέν· την κάναμε ορατό πρόβλημα για το επόμενο βήμα.

## QA check

```python
for column in ["longitude", "latitude", "elevation_m"]:
    assert pd.api.types.is_numeric_dtype(df[column])
```

## GeoTip

Το `errors="coerce"` είναι χρήσιμο σε exploratory cleaning, αλλά σε παραγωγικό workflow πρέπει να καταγράφεις πόσες τιμές μετατράπηκαν σε `NaN`.
