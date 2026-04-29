SYNTHESE ETAPES  AJOUT UTILISATEURS ET PERMISSIONS
simuler 
    séparation des services
    gestion utilisateurs
    gestion groupes
    permissions fichiers
    sécurité entreprise
    logique admin système


1. Structure entreprise

ENTREPRISE
├── rh
├── dev
└── it

2. Création des utilisateurs
sudo adduser alice   
sudo adduser bob  
sudo adduser charlie   


3. Création des groupes
sudo groupadd rh
sudo groupadd dev
sudo groupadd it


4. Affectation des utilisateurs
sudo usermod -aG rh alice
sudo usermod -aG dev bob
sudo usermod -aG it charlie


5. Création des dossiers
mkdir entreprise
cd entreprise
mkdir rh dev it


6. Sécurisation des dossiers

1) changer le propriétaire des dossiers
En entreprise, on utilise souvent -R uniquement sur des répertoires de projet, jamais sur /etc, /var, /usr, etc.
chown :rh rh  Change le groupe du dossier
chown -R :rh rh  Change le groupe du dossier + contenu

sudo chown -R :rh rh
sudo chown -R :dev dev
sudo chown -R :it it


Puis on attribue les permissions:

chmod 770 rh
chmod 770 dev
chmod 770 it


7. Résultat logique
Dossier	accès
RH	RH uniquement
DEV	DEV uniquement
IT	IT uniquement


8. Test réel
su alice    (mettre mdp de alice)
cd rh   => OK
cd dev  => interdit

exit pour revenir á l'utilisateur initial



9. Ajout sécurité sudo (IT uniquement)
sudo usermod -aG sudo charlie
=> Charlie devient admin IT

verif avec sudo -l -U nom utilisateur





