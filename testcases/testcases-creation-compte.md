# Test Cases — Création de Compte

## User Story
En tant qu’utilisateur, je souhaite créer un compte en renseignant mon email, mot de passe et confirmation du mot de passe afin d’accéder à l’application.

---

## TC-REG-001 — Création de compte valide

### Objectif
Vérifier que l’utilisateur peut créer un compte avec des informations valides.

### Préconditions
- La page d'inscription /register est accessible.
- L’utilisateur ne possède pas déjà un compte avec cet email.

### Étapes
1. Ouvrir la page /register.
2. Saisir un email valide (ex : test@example.com).
3. Saisir un mot de passe valide (ex : Test1234).
4. Saisir la même valeur dans le champ de confirmation du mot de passe.
5. Cliquer sur *« Créer un compte »*.

### Données de test
- Email : test@example.com
- Mot de passe : Test1234
- Confirmation : Test1234

### Résultat attendu
- Le compte est créé avec succès.
- L’utilisateur est redirigé vers le tableau de bord *ou* un message s’affiche :  
  *« Compte créé avec succès. »*

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-REG-002 — Email invalide

### Objectif
Vérifier que la validation front-end et/ou back-end refuse un email au format incorrect.

### Préconditions
- La page d'inscription /register est accessible.

### Étapes
1. Ouvrir la page /register.
2. Saisir un email invalide (ex : test@).
3. Saisir un mot de passe valide.
4. Saisir une confirmation identique.
5. Cliquer sur *« Créer un compte »*.

### Données de test
- Email : test@
- Mot de passe : Test1234
- Confirmation : Test1234

### Résultat attendu
- Un message d’erreur apparaît sous le champ email :  
  *« Email invalide. »*
- Le compte n’est pas créé.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-REG-003 — Mots de passe différents

### Objectif
Vérifier que la confirmation du mot de passe doit être identique au mot de passe.

### Préconditions
- La page d'inscription /register est accessible.

### Étapes
1. Ouvrir la page /register.
2. Saisir un email valide.
3. Saisir un mot de passe : Test123.
4. Saisir une confirmation différente : Test1234.
5. Cliquer sur *« Créer un compte »*.

### Données de test
- Email : test@example.com
- Mot de passe : Test123
- Confirmation : Test1234

### Résultat attendu
- Un message d’erreur s’affiche :  
  *« Les mots de passe ne correspondent pas. »*
- Le compte n’est pas créé.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-REG-004 — Champs vides

### Objectif
Vérifier que tous les champs obligatoires sont soumis à une validation.

### Préconditions
- La page d'inscription /register est accessible.

### Étapes
1. Ouvrir la page /register.
2. Cliquer directement sur *« Créer un compte »* sans remplir les champs.

### Données de test
- Aucun champ rempli.

### Résultat attendu
- Messages d’erreur affichés pour chaque champ requis, tels que :
  - *« Email requis. »*
  - *« Mot de passe requis. »*
  - *« Confirmation du mot de passe requise. »*
- Aucun compte n’est créé.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente