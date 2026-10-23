# GP06 — Filtering

Το GP06 δείχνει πώς μετατρέπεις ένα σύνολο υποδομών σε στοχευμένη επιλογή features. Η ροή είναι **Κατανοώ → Ελέγχω → Επεξεργάζομαι → Επαληθεύω → Εξάγω**.

## Τι θα μάθεις

Θα γράφεις boolean συνθήκες, θα συνδυάζεις φίλτρα με `&`, `|`, `~`, θα χρησιμοποιείς `isin()`, αναζητήσεις κειμένου, αριθμητικά ranges, missing values και χωρικό περιορισμό με `.cx`. Το dataset `data/gp06/assets.csv` περιέχει σημεία υποδομών με τύπο, κατάσταση, προτεραιότητα και score.

## Πρακτική άσκηση στο Colab

[![Άνοιγμα του starter notebook στο Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp06_filtering_starter.ipynb)

## Ενδεικτική λύση

[![Άνοιγμα της λύσης στο Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp06_filtering_solution.ipynb)

## Mini Challenge και readiness checkpoint

Επίλεξε ενεργά πάρκα ή σχολεία με score τουλάχιστον 75 μέσα σε συγκεκριμένο bbox και κάνε export. Είσαι έτοιμος για GP07 όταν μπορείς να εξηγήσεις όχι μόνο ποια rows επέλεξες αλλά και γιατί το QA αποδεικνύει ότι το φίλτρο εφαρμόστηκε σωστά.
