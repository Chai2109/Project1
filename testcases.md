# testcases.md

## User Story :
En tant qu’utilisateur, je souhaite créer un compte en renseignant email, mot de passe et confirmation.

---

### Cas de Test 1 — Création de compte valide
- **Objectif :** Vérifier la création de compte avec données valides.
- **Préconditions :** Page d'inscription accessible.
- **Étapes :**
  1. Ouvrir /register
  2. Entrer email valide (ex: test@example.com)
  3. Entrer mot de passe valide (ex: Test1234)
  4. Entrer confirmation identique
  5. Cliquer "Créer un compte"
- **Données utilisées :** email=test@example.com, password=Test1234
- **Résultat attendu :** Compte créé, redirection vers dashboard ou message "Compte créé".
- **Résultat obtenu :** *[Indiquer ici ce que tu observes]* 
- **Status :** Pass / Fail

---

### Cas de Test 2 — Email invalide
- **Objectif :** Vérifier validation du format email.
- **Étapes :**
  1. Ouvrir /register
  2. Entrer "test@"
  3. Remplir autres champs valides
  4. Cliquer "Créer un compte"
- **Résultat attendu :** Message "Email invalide".
- **Résultat obtenu :** *[Indiquer ici ce que tu observes]*
- **Status :** Pass / Fail

---

### Cas de Test 3 — Mots de passe différents
- **Objectif :** Vérifier que confirmation est identique.
- **Étapes :**
  1. Entrer email valide
  2. Mot de passe = "Test123"
  3. Confirmation = "Test1234"
  4. Cliquer "Créer un compte"
- **Résultat attendu :** Message "Les mots de passe ne correspondent pas".
- **Résultat obtenu :** *[Indiquer ici ce que tu observes]*
- **Status :** Pass / Fail

---

### Cas de Test 4 — Champs vides
- **Objectif :** Vérifier champs obligatoires.
- **Étapes :**
  1. Ouvrir /register
  2. Cliquer "Créer un compte" sans remplir
- **Résultat attendu :** Messages d'erreur pour chaque champ requis.
- **Résultat obtenu :** *[Indiquer ici ce que tu observes]*
- **Status :** Pass / Fail
