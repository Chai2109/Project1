# Test Cases — Gestion des Favoris

## User Story
En tant qu’utilisateur, je souhaite pouvoir ajouter ou retirer des produits de mes favoris afin de retrouver facilement mes produits préférés.

---

## TC-FAV-001 — Ajouter un produit aux favoris

### Objectif
Vérifier que l’utilisateur peut ajouter un produit à sa liste de favoris.

### Préconditions
- L’utilisateur possède un compte valide.
- L’utilisateur est connecté.
- Le catalogue produit est accessible.

### Étapes
1. Se connecter avec un compte utilisateur valide.
2. Accéder au catalogue produit.
3. Sélectionner un produit disponible.
4. Cliquer sur le bouton *« Ajouter aux favoris »*.

### Données de test
- Produit existant : ProductID valide.

### Résultat attendu
- Le produit est ajouté à la liste des favoris.
- Un message de confirmation s’affiche : *« Produit ajouté à vos favoris. »*
- L’icône du produit change d’état (devient marquée comme favori).

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-FAV-002 — Retirer un produit des favoris

### Objectif
Vérifier que l’utilisateur peut retirer un produit de sa liste de favoris.

### Préconditions
- L’utilisateur est connecté.
- Au moins un produit est déjà présent dans la liste des favoris.

### Étapes
1. Accéder à la page *« Favoris »*.
2. Sélectionner un produit déjà marqué comme favori.
3. Cliquer sur *« Retirer des favoris »*.

### Données de test
- Produit existant dans les favoris : ProductID valide.

### Résultat attendu
- Le produit est retiré de la liste des favoris.
- Un message s’affiche : *« Produit retiré de vos favoris. »*
- L’icône revient à l’état non favori.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-FAV-003 — Ajouter un produit inexistant

### Objectif
Vérifier la gestion d’erreur lorsqu’un produit inexistant est ajouté aux favoris.

### Préconditions
- L’utilisateur est connecté.
- Le catalogue produit est accessible.

### Étapes
1. Accéder manuellement à une URL de type :  
   /add-favorite?id=<ID_invalide>.

### Données de test
- ProductID invalide ou inexistant dans la base.

### Résultat attendu
- Un message d’erreur s’affiche : *« Produit non trouvé. »*
- Aucun produit n’est ajouté à la liste des favoris.
- L’application ne plante pas (gestion correcte de l’erreur).

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-FAV-004 — Consulter la liste des favoris sans authentification

### Objectif
Vérifier la sécurité d’accès à la liste des favoris.

### Préconditions
- Aucun utilisateur n’est connecté.

### Étapes
1. Accéder directement à l’URL : /favorites.

### Données de test
- Aucune.

### Résultat attendu
- L’utilisateur est redirigé vers la page de connexion /login.
- Un message s’affiche : *« Veuillez vous connecter pour accéder à vos favoris. »*
- L’accès à la liste des favoris est refusé tant que l’utilisateur n’est pas authentifié.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente