# 1) Prix moyen de la bière par quartier
    SELECT 
    q.nom AS quartier,
    ROUND(AVG(p.prix), 2) AS prix_moyen
    FROM quartier q
    JOIN bar b ON b.id_quartier = q.id_quartier
    JOIN prix p ON p.id_bar = b.id_bar
    GROUP BY q.nom
    ORDER BY prix_moyen ASC;
# 2) Bars vendant l'IPA la moins chère

# 3) Bières vendues dans ≥ 5 bars

# 4)  Bars sans bière à moins de 6€
    SELECT 
    b.id_bar,
    b.nom,
    b.adresse
    FROM bar b
    WHERE NOT EXISTS (
    SELECT 1
    FROM prix p
    WHERE p.id_bar = b.id_bar
    AND p.prix < 6
    );

# 5) Top bar avec panier moyen maximum
    SELECT 
    b.id_bar,
    b.nom,
    ROUND(AVG(p.prix), 2) AS panier_moyen
    FROM bar b
    JOIN prix p ON p.id_bar = b.id_bar
    GROUP BY b.id_bar, b.nom
    ORDER BY panier_moyen DESC;