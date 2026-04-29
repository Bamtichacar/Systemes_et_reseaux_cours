GESTION DES UTILISATEURS

on va formaliser ce qui a déjà été commencé, mais proprement comme en entreprise sur Ubuntu.


1. Créer un utilisateur

    sudo adduser testuser

=> crée :

    utilisateur
    dossier /home/testuser
    mot de passe


2. Supprimer un utilisateur

* Supprimer un utilisateur : ATTENTION garde ses fichiers

    sudo deluser testuser

=> supprime user


 * supprimer complètement : supprime aussi son dossier

    sudo deluser --remove-home testuser


3. Voir les utilisateurs

    cat /etc/passwd

=> liste tous les utilisateurs système


4. Voir les groupes

    cat /etc/group


5. Ajouter à un groupe

    sudo usermod -aG dev user1


6. Voir les groupes d’un user

    groups user1


7. Bonnes pratiques entreprise

toujours :

    créer un user par personne
    utiliser des groupes
    limiter sudo
    éviter root


8. complément sur les permissions

La différence entre :

    sudo chown :projet projet
et

    sudo chown -R :projet projet

est majeure : l’un agit uniquement sur le dossier lui‑même, l’autre agit sur le dossier + tout son contenu récursivement.

    1) sudo chown :projet projet
Cette commande change uniquement le groupe propriétaire du dossier projet.

Le propriétaire ne change pas

Le groupe devient projet

Aucun fichier à l’intérieur n’est modifié

C’est l’équivalent de :

sudo chown root:projet projet
(si le propriétaire actuel est root)

=> Utile quand on veut juste changer le groupe du dossier principal.

    2) sudo chown -R :projet projet
L’option -R = récursive.

Cela change le groupe pour :

le dossier projet

tous les sous‑dossiers

tous les fichiers

Exemple :
Si projet contient 10 000 fichiers, ils seront tous modifiés.

=> C’est ce qu’on utilise quand on veut que tout le contenu appartienne au groupe projet.

 Résumé clair
Commande	                Effet	                                  Portée 
chown :projet projet	    Change le groupe du dossier	              Dossier uniquement
chown -R :projet projet	    Change le groupe du dossier + contenu	  Récursif


Attention aux effets du -R
Peut casser des permissions si on modifie des fichiers système

Peut être long sur de gros dossiers

Peut modifier des fichiers qui ne devraient pas changer de groupe

En entreprise, on utilise souvent -R uniquement sur des répertoires de projet, jamais sur /etc, /var, /usr, etc.




8. Question rapide

Quelle est la différence entre :

deluser user1

et

deluser --remove-home user1


=> 
deluser user1 va uniquement supprimer l utilisateur tandis que deluser --remove-home user1 va supprimer l utilisateur ainsi que ses fichiers et dossiers si ils existent


en résumé 
deluser user1 → supprime seulement le compte
deluser --remove-home user1 → supprime le compte + son dossier /home/user1 et ses fichiers

Petite précision 

En réalité :

les fichiers ailleurs sur le système (hors /home) ne sont pas supprimés automatiquement
ils restent avec l’ancien UID (propriétaire “fantôme”)

=> en entreprise, on fait souvent un nettoyage supplémentaire