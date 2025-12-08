# Bug Report — Réinitialisation du Mot de Passe par Numéro de Téléphone

## Informations Générales
- *Projet :* Application de réinitialisation par téléphone
- *Date :* 08/12/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Authentification / Mot de passe oublié (par téléphone)

---

## BUG-301 — Numéro invalide accepté

### Description
Le système accepte un numéro de téléphone non enregistré ou invalide et ne renvoie pas le message d’erreur approprié.  
Dans certains cas, aucun message d’erreur n’est affiché, ce qui laisse penser que l’opération a été prise en compte.

### Préconditions
- La page /forgot-password est accessible.

### Étapes pour reproduire
1. Ouvrir /forgot-password.
2. Saisir un numéro inexistant, ex: +212611111111.
3. Cliquer sur *« Envoyer le code de réinitialisation »*.

### Résultat attendu
- Message d’erreur clair :  
  *« Numéro non trouvé. »*
- Aucun code SMS n’est envoyé.

### Résultat obtenu
TBD (à compléter après reproduction).

### Impact
- Confusion pour l’utilisateur.
- Possible faille d’énumération d'utilisateurs si mauvaise gestion du retour.
- Risque de comportement incohérent.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-301](screenshots/screenshot1.png)

---

## BUG-302 — Mots de passe différents acceptés

### Description
Le système accepte un nouveau mot de passe et une confirmation différentes sans afficher de message d’erreur, permettant potentiellement l’enregistrement d’un mot de passe non voulu.

### Préconditions
- L’utilisateur a reçu un code SMS valide.

### Étapes pour reproduire
1. Entrer un code OTP valide.
2. Saisir un nouveau mot de passe : NewPass123.
3. Saisir une confirmation différente : NewPass124.
4. Cliquer sur *« Confirmer »*.

### Résultat attendu
- Message d’erreur :  
  *« Les mots de passe ne correspondent pas. »*
- Aucun changement ne doit être effectué.

### Résultat obtenu
TBD.

### Impact
- Risque majeur de sécurité si le système enregistre un mot de passe inattendu.
- Mauvaise expérience utilisateur.
- Comportement contraire aux normes d’authentification.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-302](screenshots/screenshot2.png)

---

## BUG-303 — Absence de messages pour les champs obligatoires

### Description
Lorsque l’utilisateur clique sur « Envoyer » ou « Confirmer » sans remplir les champs obligatoires (numéro, code OTP, mot de passe), certains messages d’erreur ne s’affichent pas.

### Préconditions
- La page /forgot-password est accessible.

### Étapes pour reproduire
1. Ouvrir /forgot-password.
2. Cliquer sur *« Envoyer »* sans entrer de numéro.
3. Aller sur l’étape suivante (si possible).
4. Cliquer sur *« Confirmer »* sans remplir les champs.

### Résultat attendu
Des messages d’erreur doivent s’afficher pour chaque champ requis :
- *« Numéro requis »*
- *« Code requis »*
- *« Mot de passe requis »*
- *« Confirmation requise »*

### Résultat obtenu
TBD.

### Impact
- Manque de feedback utilisateur.
- Validation non conforme aux standards.
- Risque d’erreurs silencieuses.

### Priorité
Moyenne

### Sévérité
Majeur

### Statut
Nouveau

### Pièce Jointe
![BUG-303](screenshots/screenshot3.png)