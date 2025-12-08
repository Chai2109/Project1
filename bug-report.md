# Bug Report — Application de création de compte

## Informations générales
- **Projet :** Application de création de compte
- **Date :** 25/11/2025
- **Testeur :** Chaimae
- **Environnement :** Navigateur Chrome / Version 120.x / Windows 10
- **Version de l’application :** 1.0

---

## Bug 1 — Email invalide accepté
- **ID du bug :** BUG-001
- **Description :** Le système accepte des emails au format invalide (ex: test@) sans afficher de message d’erreur.
- **Préconditions :** Page d'inscription accessible
- **Étapes pour reproduire :**
  1. Ouvrir /register
  2. Entrer "test@" dans le champ email
  3. Remplir les autres champs correctement
  4. Cliquer sur "Créer un compte"
- **Résultat attendu :** Message d’erreur "Email invalide"
- **Résultat obtenu :** TBD
- **Priorité :** Haute
- **Sévérité :** Critique
- **Statut :** Nouveau
- **Capture d’écran / preuve :** ![BUG-001](screenshots/screenshot1.png)
---

## Bug 2 — Mots de passe différents
- **ID du bug :** BUG-002
- **Description :** La confirmation du mot de passe ne correspond pas au mot de passe mais le formulaire continue.
- **Préconditions :** Page d'inscription accessible
- **Étapes pour reproduire :**
  1. Entrer email valide
  2. Mot de passe : "Test123"
  3. Confirmation : "Test1234"
  4. Cliquer "Créer un compte"
- **Résultat attendu :** Message d’erreur "Les mots de passe ne correspondent pas"
- **Résultat obtenu :** TBD
- **Priorité :** Haute
- **Sévérité :** Critique
- **Statut :** Nouveau
- **Capture d’écran / preuve :** ![BUG-002](screenshots/screenshot2.png)
---

## Bug 3 — Champs obligatoires vides
- **ID du bug :** BUG-003
- **Description :** Si l’utilisateur clique sur "Créer un compte" sans remplir les champs, certains messages d’erreur n’apparaissent pas.
- **Préconditions :** Page d'inscription accessible
- **Étapes pour reproduire :**
  1. Ouvrir /register
  2. Cliquer "Créer un compte" sans remplir les champs
- **Résultat attendu :** Messages d’erreur pour chaque champ requis (ex: "Email requis", "Mot de passe requis")
- **Résultat obtenu :** TBD
- **Priorité :** Moyenne
- **Sévérité :** Majeur
- **Statut :** Nouveau
- **Capture d’écran / preuve :** ![BUG-003](screenshots/screenshot3.png)
