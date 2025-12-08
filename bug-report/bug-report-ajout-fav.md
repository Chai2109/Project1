# Bug Report — Gestion des Favoris

## Informations Générales
- *Projet :* Application e-commerce
- *Date :* 08/12/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Produits / Favoris (Add & Remove)

---

## BUG-101 — Produit non ajouté aux favoris

### Description
Lorsqu’un utilisateur clique sur *« Ajouter aux favoris »*, aucune action n’est effectuée pour certains produits.  
Ni message de confirmation, ni mise à jour visuelle, ni ajout en base.

### Préconditions
- Utilisateur connecté.
- Produit disponible dans le catalogue.

### Étapes pour reproduire
1. Se connecter avec un compte valide.
2. Aller dans le catalogue produit.
3. Cliquer sur *« Ajouter aux favoris »* pour un produit spécifique.
4. Ouvrir la page des favoris.

### Résultat attendu
- Message affiché :  
  *« Produit ajouté à vos favoris. »*
- L’icône du produit doit changer d’état.
- Le produit doit apparaître dans la liste des favoris.

### Résultat obtenu
TBD (à documenter après test)

### Impact
- Fonction essentielle non opérationnelle.
- Mauvaise expérience utilisateur.
- Perte potentielle de ventes (fonction clé dans un e-commerce).
- Incohérence entre la base et l’UI.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Capture d’Écran
![BUG-101](screenshots/favorites1.png)

---

## BUG-102 — Retrait des favoris échoue

### Description
Le bouton *« Retirer des favoris »* ne supprime pas toujours le produit.  
L’UI ne se met pas à jour ou la base ne prend pas en compte la demande.

### Préconditions
- Utilisateur connecté.
- Le produit est déjà présent dans la liste des favoris.

### Étapes pour reproduire
1. Aller dans *Mes Favoris*.
2. Cliquer sur *« Retirer des favoris »* pour un produit.
3. Recharger la page.

### Résultat attendu
- Le produit doit être retiré.
- Message affiché :  
  *« Produit retiré de vos favoris. »*
- Le produit ne doit plus apparaître ni en base ni en UI.

### Résultat obtenu
TBD

### Impact
- Fonctionnalité incomplète / instable.
- Confusion utilisateur (produit semble retiré mais revient).
- Incohérence entre front et backend.
- Perte de confiance dans l’application.

### Priorité
Moyenne

### Sévérité
Majeur

### Statut
Nouveau

### Capture d’Écran
![BUG-102](screenshots/favorites2.png)