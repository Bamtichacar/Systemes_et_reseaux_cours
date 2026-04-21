Gestion des fichiers
copier (cp)
déplacer (mv)
lire (cat, less)
supprimer (rm)



Commandes essentielles

1. Copier des fichiers — cp

Exemple

cp fichier1.txt copie.txt

=> copie fichier1.txt vers copie.txt

Copier un dossier

cp -r dossier1 dossier2

=> -r = récursif (obligatoire pour dossiers)


2. Déplacer / renommer — mv

Exemple

mv fichier1.txt dossier/

=> déplace le fichier


Renommer

mv fichier1.txt nouveau.txt



3. Lire un fichier — cat

cat fichier.txt

=> affiche le contenu



4. Lire proprement — less

less fichier.txt

=> navigation avec :

flèches ↑ ↓
quitter : q


5. ⚠️ Supprimer — rm

rm fichier.txt

⚠️ Supprimer un dossier

rm -r dossier


### ⚠️ DANGER (à connaître)

rm -rf /

=> supprime tout le système ❌
(ne jamais faire ça)



6. Voir contenu d’un dossier

ls -l

=> affiche :

permissions
taille
propriétaire