# GP10 — Clip / Intersection / Overlay

Το GP10 είναι το πρώτο module όπου η χωρική πράξη αλλάζει ουσιαστικά τις geometries. Θα περιορίσεις δεδομένα σε περιοχή μελέτης και θα συνδυάσεις polygon layers. Η ροή είναι **Κατανοώ → Ελέγχω → Επεξεργάζομαι → Επαληθεύω → Εξάγω**.

## Τι θα μάθεις

Θα ξεχωρίζεις `clip`, spatial join και overlay/intersection, θα δουλεύεις με mask, θα ελέγχεις validity και empty geometries και θα συγκρίνεις area πριν/μετά. Το `data/gp10/` περιέχει study area, land-use polygons και protected zone.

| Εργαλείο | Τι αλλάζει στη geometry | Τι γίνεται στα attributes | Πότε το χρησιμοποιούμε |
|---|---|---|---|
| Clip | Κόβει το input στη mask | Κρατά κυρίως attributes του input | Περιοχή μελέτης |
| Spatial join | Δεν κόβει geometry | Προσθέτει attributes βάσει σχέσης | Αντιστοίχιση features |
| Overlay / intersection | Δημιουργεί γεωμετρία τομής | Συνδυάζει attributes και των δύο layers | Ανάλυση κοινής έκτασης |

## Πρακτική άσκηση στο Colab

[![Άνοιγμα του starter notebook στο Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp10_clip_intersection_overlay_starter.ipynb)

## Ενδεικτική λύση

[![Άνοιγμα της λύσης στο Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp10_clip_intersection_overlay_solution.ipynb)

## Mini Challenge και readiness checkpoint

Κόψε το land-use στη study area και βρες την τομή του με την protected zone. Είσαι έτοιμος όταν μπορείς να εξηγήσεις γιατί αλλάζουν rows, geometries, attributes και areas.
