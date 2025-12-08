# Test Cases — Modification de Profil

## User Story
En tant qu’utilisateur, je souhaite modifier les informations de mon profil (nom, email, téléphone, mot de passe, photo) afin de garder mes données à jour.

---

## TC-PROF-001 — Mise à jour valide du profil

### Objectif
Vérifier que l’utilisateur peut modifier son profil avec des données valides.

### Préconditions
- L’utilisateur est connecté.
- La page /profile est accessible.

### Étapes
1. Aller sur /profile.
2. Modifier le nom → Chaimae Test.
3. Modifier l’email → chaimae@example.com.
4. Modifier le numéro → 0612345678.
5. Cliquer sur *« Enregistrer »*.

### Données de test
- Nom valide
- Email valide
- Numéro valide (format marocain ou international)

### Résultat attendu
- Les informations sont mises à jour.
- Un message apparaît : *« Profil mis à jour avec succès. »*

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-PROF-002 — Email invalide

### Objectif
Vérifier que la modification du profil échoue si le format email est incorrect.

### Préconditions
- L’utilisateur est connecté.

### Étapes
1. Aller sur /profile.
2. Saisir un email invalide : test@.
3. Cliquer sur *« Enregistrer »*.

### Données de test
- Email : test@

### Résultat attendu
- Un message d’erreur apparaît :  
  *« Email invalide. »*
- La mise à jour du profil est refusée.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-PROF-003 — Numéro de téléphone invalide

### Objectif
Vérifier que la mise à jour du profil est bloquée si le numéro de téléphone est invalide.

### Préconditions
- L’utilisateur est connecté.

### Étapes
1. Aller sur /profile.
2. Entrer 123 comme numéro.
3. Cliquer sur *« Enregistrer »*.

### Données de test
- Numéro : 123 (trop court / invalide)

### Résultat attendu
- Un message apparaît :  
  *« Numéro de téléphone invalide. »*
- Aucune modification n’est enregistrée.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-PROF-004 — Mot de passe trop court

### Objectif
Vérifier que le système refuse un mot de passe ne respectant pas la longueur minimale.

### Préconditions
- L’utilisateur est connecté.

### Étapes
1. Aller sur /profile.
2. Saisir un mot de passe : 123.
3. Cliquer sur *« Enregistrer »*.

### Données de test
- Mot de passe : 123 (moins de 6–8 caractères selon la règle)

### Résultat attendu
- Un message apparaît :  
  *« Mot de passe trop court. »*
- Le profil n’est pas mis à jour.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-PROF-005 — Confirmation du mot de passe incorrecte

### Objectif
Vérifier que le mot de passe et sa confirmation doivent être identiques.

### Préconditions
- L’utilisateur est connecté.

### Étapes
1. Aller sur /profile.
2. Mot de passe : Test1234.
3. Confirmation : Test5678.
4. Cliquer sur *« Enregistrer »*.

### Données de test
- Mot de passe : Test1234
- Confirmation : Test5678

### Résultat attendu
- Un message apparaît :  
  *« Les mots de passe ne correspondent pas. »*
- Aucune mise à jour n’est effectuée.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-PROF-006 — Photo de profil invalide

### Objectif
Vérifier que seuls les formats d’image autorisés (PNG/JPEG) peuvent être importés.

### Préconditions
- L’utilisateur est connecté.

### Étapes
1. Aller sur /profile.
2. Télécharger un fichier non image (ex : virus.exe).
3. Cliquer sur *« Enregistrer »*.

### Données de test
- Fichier envoyé : fichier.exe

### Résultat attendu
- Un message apparaît :  
  *« Format non supporté. »*
- L’image n’est pas enregistrée.
- Le reste du profil ne doit pas être mis à jour (selon règle de ton app).

### Résultat obtenu
À compléter après exécution.

### Statut
En attente