# 1) Entités:
    - bars
    - quartiers
    - bière
    - prix bière
---
# 2) Relations:
    1. Quartier-Bar
    2. Bar-Bière
    3. Bière-Prix
---

# 3) Règles métier:
## Quartiers:
    - Un quartier ne peut avoir qu'un seul nom.      

## Bars: 
    - Un bar n'appartient qu'à un seul quartier.
    
## Bière:
    - Le nom d'une bière doit être unique dans la table des bières.
    - Le nom d'une bière peut être le même dans plusieurs bars.
    - Le degrès d'alcool doit être positif.

## Prix:
    - Le prix doit être positif.
    - Le prix d'une même bière peut varier en fonction des bars.

# 4) Attributs importants
## Quartier:
    - nom -> nom du quartier
    - id_quartier -> identifiant
## Bar: 
    - adresse -> Adresse du bar
    - nom -> Nom du bar
    - id_bar (PK) -> identifiant
    - id_quartier(FK) -> Quartier du bar
## Bière: 
    - nom -> Nom de la bière
    - type -> "Lager","IPA",etc.
    - degrés -> Degrés d'alcool
    - catégorie -> Blonde, Brune,etc.
    - id_biere(PK) -> identifiant
## Prix:
    - prix -> Prix de la bière dans ce bar
    - id_bar(FK) -> Bar
    - id_biere(FK) -> Bière


