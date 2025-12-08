# Bug Report — Création de Compte

## Informations Générales
- *Projet :* Application de création de compte
- *Date :* 25/11/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Authentification / Inscription

---

## BUG-001 — Email invalide accepté

### Description
Le système accepte un email au format invalide (ex : test@) sans afficher de message d’erreur et permet de poursuivre la création du compte.

### Préconditions
- La page /register est accessible.

### Étapes pour reproduire
1. Ouvrir /register.
2. Saisir dans le champ email : test@.
3. Remplir les autres champs correctement.
4. Cliquer sur *« Créer un compte »*.

### Résultat attendu
- Message d’erreur affiché sous le champ email :  
  *« Email invalide. »*
- Le formulaire ne doit pas être soumis.

### Résultat obtenu
TBD (à compléter après test)

### Impact
- Invalidation incorrecte d’un champ critique.
- Risque d’incohérence des données.
- UX négative et risque de faux compte.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Capture d’Écran
![BUG-001](screenshots/screenshot1.png)

---

## BUG-002 — Mots de passe différents acceptés

### Description
Lorsque le mot de passe et sa confirmation ne correspondent pas, le formulaire est tout de même validé sans message d’erreur.

### Préconditions
- La page /register est accessible.

### Étapes pour reproduire
1. Entrer un email valide.
2. Saisir un mot de passe : Test123.
3. Saisir une confirmation différente : Test1234.
4. Cliquer sur *« Créer un compte »*.

### Résultat attendu
- Message d’erreur :  
  *« Les mots de passe ne correspondent pas. »*
- La création du compte doit être bloquée.

### Résultat obtenu
TBD

### Impact
- Risque critique d’incohérence d’informations d’authentification.
- Possible perte d’accès utilisateur si ce mot de passe incorrect est enregistré.
- Non-conformité totale aux standards d’inscription sécurisée.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Capture d’Écran
![BUG-002](screenshots/screenshot2.png)

---

## BUG-003 — Absence de messages pour les champs obligatoires vides

### Description
Lorsque l'utilisateur clique sur « Créer un compte » sans remplir les champs obligatoires, certains messages d’erreur ne s’affichent pas.

### Préconditions
- La page /register est accessible.

### Étapes pour reproduire
1. Ouvrir /register.
2. Ne remplir aucun champ.
3. Cliquer sur *« Créer un compte »*.

### Résultat attendu
- Affichage des messages obligatoires :  
  - *« Email requis. »*  
  - *« Mot de passe requis. »*  
  - *« Confirmation du mot de passe requise. »*  
- Le formulaire ne doit pas être soumis.

### Résultat obtenu
TBD

### Impact
- Mauvaise expérience utilisateur.
- Validation du formulaire incorrecte.
- Risque d’erreurs backend supplémentaires.

### Priorité
Moyenne

### Sévérité
Majeur

### Statut
Nouveau

### Capture d’Écran
![BUG-003](screenshots/screenshot3.png)