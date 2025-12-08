# Test Cases — Réinitialisation de Mot de Passe

## User Story
En tant qu’utilisateur, je souhaite réinitialiser mon mot de passe en cas d’oubli, afin de pouvoir accéder à mon compte.

---

## TC-RESET-001 — Réinitialisation valide

### Objectif
Vérifier que l’utilisateur peut réinitialiser son mot de passe avec un email existant et des données valides.

### Préconditions
- La page /forgot-password est accessible.
- L’utilisateur possède un compte actif.
- Le service d’envoi d’emails est fonctionnel.

### Étapes
1. Ouvrir /forgot-password.
2. Saisir un email valide et existant : test@example.com.
3. Cliquer sur *« Envoyer le lien de réinitialisation »*.
4. Ouvrir l’email reçu et cliquer sur le lien de réinitialisation.
5. Saisir un nouveau mot de passe : NewPass123.
6. Saisir la confirmation identique.
7. Cliquer sur *« Confirmer »*.

### Données de test
- Email : test@example.com  
- Nouveau mot de passe : NewPass123  
- Confirmation : NewPass123

### Résultat attendu
- Un message confirme l’envoi du lien : *« Lien de réinitialisation envoyé. »*  
- Le lien ouvre la page de changement de mot de passe.  
- Le mot de passe est modifié avec succès.  
- L’utilisateur est redirigé vers la page de connexion avec un message :  
  *« Mot de passe réinitialisé. »*

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-002 — Email invalide ou non enregistré

### Objectif
Vérifier que le système refuse un email qui n’existe pas dans la base.

### Préconditions
- La page /forgot-password est accessible.

### Étapes
1. Ouvrir /forgot-password.
2. Entrer un email inexistant : fake@example.com.
3. Cliquer sur *« Envoyer le lien de réinitialisation »*.

### Données de test
- Email : fake@example.com

### Résultat attendu
- Un message d’erreur apparaît :  
  *« Email non trouvé. »*
- Aucun email de réinitialisation n’est envoyé.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-003 — Mots de passe différents

### Objectif
Vérifier que le nouveau mot de passe et sa confirmation doivent être identiques.

### Préconditions
- L’utilisateur dispose d’un lien valide de réinitialisation.

### Étapes
1. Ouvrir le lien de réinitialisation reçu par email.
2. Saisir un nouveau mot de passe : NewPass123.
3. Saisir une confirmation différente : NewPass124.
4. Cliquer sur *« Confirmer »*.

### Données de test
- Nouveau mot de passe : NewPass123
- Confirmation : NewPass124

### Résultat attendu
- Un message d’erreur apparaît :  
  *« Les mots de passe ne correspondent pas. »*
- Le mot de passe n’est pas modifié.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-RESET-004 — Champs vides

### Objectif
Vérifier que les champs obligatoires sont contrôlés avant l’envoi.

### Préconditions
- La page /forgot-password est accessible *ou*
- La page de réinitialisation (nouveau mot de passe) est accessible.

### Étapes (2 scénarios possibles)
#### *Scénario A — Email vide*
1. Ouvrir /forgot-password.
2. Cliquer sur *« Envoyer le lien »* sans renseigner d’email.

#### *Scénario B — Nouveau mot de passe vide*
1. Ouvrir le lien de réinitialisation.
2. Cliquer sur *« Confirmer »* sans remplir les champs.

### Données de test
- Aucun champ rempli.

### Résultat attendu
- Message(s) d’erreur approprié(s) :  
  - *« Email requis. »*  
  - *« Mot de passe requis. »*  
  - *« Confirmation requise. »*
- Aucun email n’est envoyé et aucun changement n’est effectué.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente