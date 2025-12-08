# Test Cases — Réinitialisation de Mot de Passe par Téléphone

## User Story
En tant qu’utilisateur, je souhaite réinitialiser mon mot de passe en utilisant mon numéro de téléphone afin de pouvoir accéder à mon compte.

---

## TC-RESET-PHONE-001 — Réinitialisation valide

### Objectif
Vérifier qu'un utilisateur peut réinitialiser son mot de passe avec un numéro valide, un code SMS correct et des informations valides.

### Préconditions
- La page /forgot-password est accessible.
- L’utilisateur possède un compte actif associé au numéro.
- Le service SMS/OTP fonctionne.

### Étapes
1. Ouvrir /forgot-password.
2. Saisir un numéro valide : +212600000000.
3. Cliquer sur *« Envoyer le code de réinitialisation »*.
4. Saisir le code OTP reçu par SMS.
5. Saisir le nouveau mot de passe : NewPass123.
6. Saisir la confirmation identique.
7. Cliquer sur *« Confirmer »*.

### Données de test
- Numéro : +212600000000
- OTP : code valide reçu
- Nouveau mot de passe : NewPass123
- Confirmation : NewPass123

### Résultat attendu
- Un message confirme l’envoi du code SMS : *« Code envoyé. »*
- Le code OTP est accepté.
- Le mot de passe est mis à jour.
- L’utilisateur est redirigé vers la page de connexion avec le message :  
  *« Mot de passe réinitialisé. »*

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-PHONE-002 — Numéro invalide ou non enregistré

### Objectif
Vérifier que le système rejette un numéro introuvable ou invalide.

### Préconditions
- La page /forgot-password est accessible.

### Étapes
1. Ouvrir /forgot-password.
2. Saisir un numéro incorrect ou non existant : +212611111111.
3. Cliquer sur *« Envoyer le code de réinitialisation »*.

### Données de test
- Numéro : +212611111111

### Résultat attendu
- Message d’erreur affiché :  
  *« Numéro non trouvé. »*
- Aucun code SMS n'est envoyé.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-PHONE-003 — Mots de passe différents

### Objectif
Vérifier que le mot de passe et sa confirmation doivent obligatoirement correspondre.

### Préconditions
- L’utilisateur a reçu un code OTP valide.

### Étapes
1. Saisir le code OTP reçu.
2. Saisir le nouveau mot de passe : NewPass123.
3. Saisir une confirmation différente : NewPass124.
4. Cliquer sur *« Confirmer »*.

### Données de test
- Nouveau mot de passe : NewPass123
- Confirmation : NewPass124

### Résultat attendu
- Message d’erreur affiché :  
  *« Les mots de passe ne correspondent pas. »*
- Le mot de passe n’est pas modifié.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-PHONE-004 — Champs vides

### Objectif
Vérifier que les champs obligatoires (numéro, OTP, mot de passe) sont validés.

### Préconditions
- La page /forgot-password est accessible.

### Étapes (2 scénarios)
#### *Scénario A — Numéro vide*
1. Ouvrir /forgot-password.
2. Cliquer sur *« Envoyer le code »* sans numéro.

#### *Scénario B — OTP ou mot de passe vide*
1. Arriver sur la page de saisie du code (après étape d'envoi).
2. Cliquer sur *« Confirmer »* sans remplir les champs.

### Données de test
- Aucun champ rempli.

### Résultat attendu
- Messages d’erreurs apparaissent :
  - *« Numéro requis. »*
  - *« Code requis. »*
  - *« Mot de passe requis. »*
  - *« Confirmation requise. »*
- Aucune action n’est effectuée.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente