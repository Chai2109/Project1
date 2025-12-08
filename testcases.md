# Test Cases — Création de compte

## User Story
En tant qu’utilisateur, je souhaite créer un compte en renseignant mon email, mot de passe et confirmation du mot de passe, afin d’accéder à l’application.

---

### Cas de Test 1 — Création de compte valide
- **Objectif :** Vérifier la création de compte avec des données valides.
- **Préconditions :** Page d'inscription accessible.
- **Étapes :**
  1. Ouvrir /register
  2. Entrer email valide (ex: test@example.com)
  3. Entrer mot de passe valide (ex: Test1234)
  4. Entrer confirmation identique
  5. Cliquer sur "Créer un compte"
- **Données utilisées :** email=test@example.com, password=Test1234
- **Résultat attendu :** Compte créé, redirection vers le dashboard ou message "Compte créé".
- **Résultat obtenu :** TBD
- **Status :** En attente

---

### Cas de Test 2 — Email invalide
- **Objectif :** Vérifier la validation du format de l'email.
- **Préconditions :** Page d'inscription accessible.
- **Étapes :**
  1. Ouvrir /register
  2. Entrer un email invalide (ex: test@)
  3. Remplir les autres champs valides
  4. Cliquer sur "Créer un compte"
- **Résultat attendu :** Message "Email invalide"
- **Résultat obtenu :** TBD
- **Status :** En attente

---

### Cas de Test 3 — Mots de passe différents
- **Objectif :** Vérifier que la confirmation du mot de passe correspond au mot de passe.
- **Préconditions :** Page d'inscription accessible.
- **Étapes :**
  1. Entrer un email valide
  2. Mot de passe : "Test123"
  3. Confirmation : "Test1234"
  4. Cliquer sur "Créer un compte"
- **Résultat attendu :** Message "Les mots de passe ne correspondent pas"
- **Résultat obtenu :** TBD
- **Status :** En attente

---

### Cas de Test 4 — Champs vides
- **Objectif :** Vérifier que tous les champs obligatoires sont renseignés.
- **Préconditions :** Page d'inscription accessible.
- **Étapes :**
  1. Ouvrir /register
  2. Cliquer sur "Créer un compte" sans remplir les champs
- **Résultat attendu :** Messages d'erreur pour chaque champ requis (ex: "Email requis", "Mot de passe requis")
- **Résultat obtenu :** TBD
- **Status :** En attente
