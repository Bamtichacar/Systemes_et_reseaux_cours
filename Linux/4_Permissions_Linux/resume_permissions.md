# Permissions Linux

## chmod
Permet de modifier les permissions
chmod 777 nomfichier => Donner tous les droits
    ex : chmod 755 script.sh
chmod 444 nomfichier => Donner lecture seule
    ex : chmod 444 fichier.txt
chmod 644 nomfichier.txt => Donner droits lecture et écriture au propriétaire et lecture seule pour les autres
    ex : chmod 644 fichier.txt


Les permissions numériques sont toujours données sous la forme UGO :
U = User (propriétaire)
G = Group (groupe)
O = Others (autres)

Chaque chiffre est la somme de :
4 = lecture (r)
2 = écriture (w)
1 = exécution (x)


## chown
Permet de changer le propriétaire
    ex : sudo chown user1 fichier.txt

## r w x
read / write / execute


---------

Permissions Linux (TRÈS IMPORTANT)

chmod
chown
sécurité fichiers

=> notion clé en entreprise


