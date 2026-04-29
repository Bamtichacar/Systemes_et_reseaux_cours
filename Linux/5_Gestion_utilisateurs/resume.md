# Gestion utilisateurs Linux

## adduser
Créer un utilisateur
    sudo adduser nomutilisateur

## deluser
Supprimer un utilisateur mais conserve ses fichiers
    sudo deluser nomutilisateur
        => supprime seulement le compte

Supprimer un utilisateur et supprime aussi son dossier et ses fichiers
    sudo deluser --remove-home nomutilisateur
        => supprime le compte + son dossier /home/user1 et ses fichiers
        les fichiers ailleurs sur le système (hors /home) ne sont pas supprimés automatiquement
        ils restent avec l’ancien UID (propriétaire “fantôme”)
            => en entreprise, on fait souvent un nettoyage supplémentaire

## usermod
Modifier utilisateur
Ajouter à un groupe = assigner
    sudo usermod -aG dev user1

## groups
Voir les groupes
    cat /etc/group

Voir les groupes d’un user
    groups user1

## passwd
Voir les utilisateurs (liste tous les utilisateurs système)
    cat /etc/passwd


