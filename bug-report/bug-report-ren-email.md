# Bug Report — Réinitialisation de Mot de Passe (par Email)

## Informations Générales
- *Projet :* Application de réinitialisation de mot de passe
- *Date :* 08/12/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Authentification / Mot de passe oublié (Email)

---

## BUG-201 — Email invalide accepté

### Description
Lorsqu’un utilisateur saisit un email inexistant ou non enregistré, le système ne renvoie aucun message d’erreur ou renvoie un message incorrect.  
Cela laisse penser que l’opération de réinitialisation a été acceptée.

### Préconditions
- La page /forgot-password est accessible.

### Étapes pour reproduire
1. Ouvrir /forgot-password.
2. Saisir un email inexistant, ex : fake@example.com.
3. Cliquer sur *« Envoyer le lien de réinitialisation »*.

### Résultat attendu
- Un message d’erreur clair apparaît :  
  *« Email non trouvé. »*
- Aucune tentative d’envoi d’email ne doit être effectuée.

### Résultat obtenu
TBD (à compléter après test)

### Impact
- Confusion utilisateur : il pense que le lien a été envoyé.
- Fail potentiel d'énumération d’emails (risque de sécurité si réponse non uniforme).
- UX non conforme aux standards d’authentification.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-201](screenshots/screenshot1.png)

---

## BUG-202 — Mots de passe différents acceptés

### Description
Le système accepte un nouveau mot de passe et une confirmation différente sans afficher de message d’erreur.  
Cela peut aboutir à un mot de passe incorrect enregistré ou à un comportement inattendu.

### Préconditions
- L’utilisateur a cliqué sur un lien de réinitialisation valide reçu par email.

### Étapes pour reproduire
1. Ouvrir le lien de réinitialisation dans l’email.
2. Saisir un nouveau mot de passe : NewPass123.
3. Saisir une confirmation différente : NewPass124.
4. Cliquer sur *« Confirmer »*.

### Résultat attendu
- Message d’erreur affiché :  
  *« Les mots de passe ne correspondent pas. »*
- Aucun changement ne doit être appliqué.

### Résultat obtenu
TBD

### Impact
- Risque de réinitialisation incorrecte du mot de passe.
- Non-respect des règles d’authentification (critique).
- Forte frustration utilisateur.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-202](screenshots/screenshot2.png)

---

## BUG-203 — Absence de messages d’erreur pour champs obligatoires

### Description
Lorsque l’utilisateur clique sur « Envoyer » ou « Confirmer » sans remplir les champs requis (email, mot de passe, confirmation), certains messages d’erreur ne s’affichent pas.

### Préconditions
- La page /forgot-password est accessible ou la page de définition du nouveau mot de passe.

### Étapes pour reproduire
1. Sur /forgot-password, cliquer sur *« Envoyer »* sans saisir d’email.  
2. Sur la page du nouveau mot de passe, cliquer sur *« Confirmer »* sans remplir les champs.

### Résultat attendu
Des messages d’erreur clairs doivent apparaître :  
- *« Email requis. »*  
- *« Mot de passe requis. »*  
- *« Confirmation requise. »*

### Résultat obtenu
TBD

### Impact
- Mauvaise expérience utilisateur.
- Impossible de comprendre pourquoi l’action échoue.
- Invalidations UI manquantes → risque d’erreurs silencieuses.

### Priorité
Moyenne

### Sévérité
Majeur

### Statut
Nouveau

### Pièce Jointe
![BUG-203](screenshots/screenshot3.png)