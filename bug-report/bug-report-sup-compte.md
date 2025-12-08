# Bug Report — Suppression de Compte

## Informations Générales
- *Projet :* Application de gestion de compte
- *Date :* 29/11/2025
- *Testeur :* Chaimae
- *Environnement :* Chrome 120.x / Windows 10
- *Version de l’application :* 1.0
- *Module concerné :* Profil / Paramètres / Suppression de compte

---

## BUG-DEL-001 — Suppression effectuée sans confirmation

### Description
Lors de la suppression du compte, aucune popup de confirmation ne s'affiche. La suppression est déclenchée immédiatement après le clic sur *« Supprimer mon compte »*, entraînant une suppression accidentelle.

### Préconditions
- Utilisateur connecté.
- Page *Profil > Paramètres* accessible.

### Étapes pour reproduire
1. Se connecter avec un compte valide.
2. Accéder à *Profil > Paramètres*.
3. Cliquer sur *« Supprimer mon compte »*.
4. Observer l’absence de popup.

### Résultat attendu
Une popup de confirmation doit s’afficher :  
> *« Êtes-vous sûr de vouloir supprimer votre compte ? Oui / Annuler »*  
La suppression ne doit être effectuée qu’après confirmation explicite.

### Résultat obtenu
Le compte est supprimé immédiatement sans aucune confirmation.

### Impact
- Risque majeur de suppression accidentelle.
- Perte irréversible des données utilisateur.

### Priorité
Haute

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-DEL-001](screenshots/delete_account_bug.png)

---

## BUG-DEL-002 — Bouton "Annuler" non fonctionnel

### Description
Lorsque l’utilisateur clique sur *« Annuler »* dans la popup de confirmation, la suppression est quand même effectuée.

### Préconditions
- Popup de confirmation affichée.

### Étapes pour reproduire
1. Cliquer sur *« Supprimer mon compte »*.
2. Dans la popup, cliquer sur *« Annuler »*.
3. Observer le comportement.

### Résultat attendu
- La suppression doit être annulée.
- Le compte doit rester actif.
- L’utilisateur doit rester sur la page du profil.

### Résultat obtenu
Le compte est supprimé malgré l’annulation.

### Impact
- Fonctionnement inverse de la logique utilisateur.
- Risque élevé de suppression non consentie.
- Très mauvaise expérience utilisateur.

### Priorité
Haute

### Sévérité
Majeur

### Statut
Nouveau

### Pièce Jointe
![BUG-DEL-002](screenshots/delete_account_cancel_bug.png)

---

## BUG-DEL-003 — Route /delete-account accessible sans authentification

### Description
L’URL /delete-account peut être ouverte même si aucun utilisateur n’est connecté. Le système affiche la page de suppression au lieu de rediriger vers /login.

### Préconditions
- Aucun utilisateur connecté.

### Étapes pour reproduire
1. Ouvrir un navigateur en mode privé/incognito.
2. Accéder directement à /delete-account.

### Résultat attendu
- Redirection immédiate vers /login.
- Message affiché :  
  > *« Vous devez être connecté. »*  
- La page de suppression ne doit jamais être affichée.

### Résultat obtenu
La page de suppression s’affiche directement, exposant une action critique sans authentification.

### Impact
- Failles de sécurité très grave.
- Risque d’accès non autorisé et manipulation des comptes.
- Violation des normes OWASP.

### Priorité
Moyenne (fonctionnelle), *mais sécurité = critique*

### Sévérité
Critique

### Statut
Nouveau

### Pièce Jointe
![BUG-DEL-003](screenshots/delete_account_access_bug.png)