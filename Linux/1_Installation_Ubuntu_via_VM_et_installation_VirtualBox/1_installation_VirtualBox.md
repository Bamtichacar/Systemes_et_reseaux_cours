1_Installation_VirtualBox

Pourquoi utiliser une machine virtuelle

Avec VirtualBox on peut créer :

notre PC
 │
 ├── Linux serveur
 ├── Windows serveur
 └── client

Donc on simule une entreprise complète sur notre ordinateur.


Installer VirtualBox

Télécharger :

VirtualBox

https://www.virtualbox.org/wiki/Downloads

Choisir :

Windows hosts

Installer normalement.

Si nécessaire télécharger Visual C++ 2019 x64 et Visual C++ 2019 x86 :
ils se trouvent :
https://learn.microsoft.com/fr-fr/cpp/windows/latest-supported-vc-redist?view=msvc-170&utm_source=copilot.com

X86	https://aka.ms/vc14/vc_redist.x86.exe	Permalink pour la dernière version x86 prise en charge.

X64	https://aka.ms/vc14/vc_redist.x64.exe	Lien permanent vers la dernière version x64 prise en charge. Le package redistribuable X64 contient à la fois les binaires ARM64 et X64. Ce package facilite l'installation des binaires Visual C++ ARM64 requis lorsque le redistribuable X64 est installé sur un périphérique ARM64.

Les fichier que à choisir s’appelle généralement :

VC_redist.x64.exe


Pourquoi deux fichiers ?
x64 → pour les programmes 64 bits (ton Windows est 64 bits)

x86 → pour les programmes 32 bits (VirtualBox utilise encore certains modules 32 bits)

Installer les deux évite toutes les erreurs.