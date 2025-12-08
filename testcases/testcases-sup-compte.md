# Test Cases — Suppression de Compte

## User Story
En tant qu’utilisateur, je souhaite pouvoir supprimer mon compte en toute sécurité afin de retirer mes données de l’application.

---

## TC-DEL-001 — Suppression de compte avec confirmation

### Objectif
Vérifier que la suppression du compte fonctionne correctement lorsque l’utilisateur confirme l’action.

### Préconditions
- L’utilisateur est connecté.
- La page Profil > Paramètres est accessible.
- Le compte existe dans la base de données.

### Étapes
1. Se connecter avec un compte valide.
2. Accéder à *Profil > Paramètres*.
3. Cliquer sur *« Supprimer mon compte »*.
4. Dans la popup, cliquer sur *« Oui, supprimer »*.
5. Attendre la confirmation du serveur.

### Données de test
- Compte utilisateur valide.

### Résultat attendu
- Le compte est définitivement supprimé de la base de données.
- La session utilisateur est invalidée.
- L’utilisateur est redirigé vers la page d’accueil ou vers /login.
- Message affiché :  
  *« Votre compte a été supprimé. »*

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-DEL-002 — Annulation de la suppression

### Objectif
Vérifier que l’annulation de la confirmation empêche la suppression du compte.

### Préconditions
- L’utilisateur est connecté.
- La popup de confirmation est affichée.

### Étapes
1. Cliquer sur *« Supprimer mon compte »*.
2. Dans la popup, cliquer sur *« Annuler »*.

### Données de test
- Compte utilisateur valide.

### Résultat attendu
- La popup se ferme.
- Aucune donnée n’est supprimée.
- L’utilisateur reste dans son compte et sa session reste active.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente

---

## TC-DEL-003 — Tentative de suppression sans authentification (Sécurité)

### Objectif
Vérifier que la route de suppression est protégée contre les accès non authentifiés.

### Préconditions
- Aucun utilisateur n’est connecté.

### Étapes
1. Ouvrir un navigateur en mode privé/incognito.
2. Accéder directement à l’URL : /delete-account.

### Données de test
- Aucun login.

### Résultat attendu
- L’utilisateur est automatiquement redirigé vers la page de connexion /login.
- Message affiché :  
  *« Veuillez vous connecter. »*
- La page de suppression ne s’affiche pas.
- Aucune donnée n’est supprimée.

### Résultat obtenu
À compléter après exécution.

### Statut
En attente