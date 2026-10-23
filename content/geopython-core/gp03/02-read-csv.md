# 2. Ανάγνωση και schema

## Τι θα μάθεις

Θα φορτώσεις το CSV και θα ελέγξεις ότι τα δεδομένα έχουν τη μορφή που περιμένεις.

```python
df = pd.read_csv("data/gp03/city_assets.csv")
print("Rows:", len(df))
print("Columns:", list(df.columns))
print(df.head())
```

## Βασικοί έλεγχοι

```python
print(df.isna().sum())
print(df["asset_type"].value_counts())
print(df["condition"].value_counts())
```

Ένα schema check προστατεύει από λάθος filename, αλλαγμένο όνομα στήλης ή κενές απαραίτητες τιμές.

## GeoTip

Μην υποθέτεις ότι επειδή ένα CSV ανοίγει, είναι έτοιμο για GIS. Το `DataFrame` δεν έχει geometry ούτε CRS.
