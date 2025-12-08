# Bug Report — Modification de Profil

## Informations Générales
- *Projet :* Application — Modification du Profil
- *Date :* 30/11/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Profil / Mise à jour d’informations utilisateur

---

## BUG-PROFILE-001 — Email non mis à jour

### Description
Lorsque l’utilisateur modifie son email et clique sur « Enregistrer », un message de succès s’affiche, mais l’email affiché reste l’ancien.  
Le backend semble ignorer la nouvelle valeur ou la page ne se met pas à jour.

### Préconditions
- L'utilisateur est connecté.
- La page /profile est accessible.

### Étapes pour reproduire
1. Aller sur /profile.
2. Modifier l’adresse email.
3. Cliquer sur *« Enregistrer »*.

### Résultat attendu
- Le nouveau mail doit être enregistré en base.
- L’interface doit afficher le nouvel email.
- Un message correct doit apparaître :  
  *« Profil mis à jour avec succès. »*

### Résultat obtenu
- Le message « Succès » apparaît, mais l’ancien email reste affiché.
- Aucune mise à jour réelle n’a été effectuée.

### Impact
- Incohérence des données utilisateur.
- Blocage potentiel pour fonctionnalités dépendantes de l’email (connexion, vérification, sécurité).
- UX très perturbante.

### Priorité
Haute

### Sévérité
Majeur

### Statut
Nouveau

### Capture d’Écran
![BUG-PROFILE-001](screenshots/profile_bug1.png)

---

## BUG-PROFILE-002 — Numéro invalide accepté

### Description
Lorsqu’un numéro de téléphone invalide est saisi (ex : « 123 »), aucune validation n’est effectuée et la mise à jour est acceptée, ce qui entraîne l’enregistrement d’un numéro incorrect.

### Préconditions
- L'utilisateur est connecté.

### Étapes pour reproduire
1. Aller sur /profile.
2. Entrer un numéro invalide, ex : 123.
3. Cliquer sur *« Enregistrer »*.

### Résultat attendu
- Message d’erreur :  
  *« Numéro invalide. »*
- Refus de la mise à jour.

### Résultat obtenu
- Aucun message d’erreur.
- Le numéro est enregistré malgré son invalidité.

### Impact
- Données utilisateur incorrectes.
- Problèmes pour la récupération de compte ou notifications par SMS.
- Risque d’erreurs fonctionnelles liées à ce numéro mal formé.

### Priorité
Moyenne

### Sévérité
Majeur

### Statut
Nouveau

### Capture d’Écran
![BUG-PROFILE-002](screenshots/profile_bug2.png)

---

## BUG-PROFILE-003 — Format de photo non vérifié

### Description
Le système permet d'envoyer et d'accepter un fichier *.exe* comme photo de profil.  
Cela représente une *faille de sécurité majeure* (risque d’upload de fichiers dangereux).

### Préconditions
- L'utilisateur est connecté.

### Étapes pour reproduire
1. Aller sur /profile.
2. Sélectionner un fichier .exe.
3. Cliquer sur *« Enregistrer »*.

### Résultat attendu
- Message d’erreur :  
  *« Format non supporté. Veuillez choisir une image PNG ou JPEG. »*
- Le fichier ne doit pas être enregistré.

### Résultat obtenu
- Le fichier .exe est accepté et enregistré.

### Impact
- Failles de sécurité très critiques (risque d’exploitation, malware, injection).
- Conformité non respectée aux bonnes pratiques de validation des uploads.
- Risque d’altération du système.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Capture d’Écran
![BUG-PROFILE-003](screenshots/profile_bug3.png)