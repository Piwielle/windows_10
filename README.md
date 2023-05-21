*Dernière mise à jour : 21/05/2023*

# Installer et optimiser Windows 10
Ce site présente un guide sur comment bien installer ou réinstaller Windows 10 proprement. Il s'agit d'un guide complet, que vous devriez pouvoir suivre sans souci.

## Pourquoi ce guide.
Il existe énormément de tweaks, optimisations, tutoriels, scripts et logiciels sur internet qui vont vous promettre de doubler vos FPS, réduire votre latence, stabiliser vos FPS, et je ne sais quoi d'autre. La majorité de ces tweaks sont faux, plus à jour, n'améliorent rien, et risquent de vous forcer à réinstaller windows en cas d'erreur (et des fois même si vous avez tout suivi correctement), voire même d'endommager votre PC.
Les simples tweaks que je vais détailler ici vont garantir un pc qui sera sain, et vous aurez fait 99% du chemin concernant l'optimisation de votre PC, sans danger pour le PC, et avec tout qui fonctionnera.

Si vous souhaitez gratter le 1% restant, faites le, mais sachez que c'est à vos risques et périls, que vous allez forcément à un moment faire une connerie et devoir réinstaller windows, et le tout pour un gain de performances qui sera très très faible (globalement 100% invisible).

Voici ce que je vous conseille sur une nouvelle installation de windows. Ce sont des tweaks qui sont sans dangers pour le pc, que ce soit niveau hardware ou software. Si vous avez une question particulière durant une des étapes, n'hésitez pas à demander sur [Discord](https://discord.gg/informatique) !

## Passer à Windows 11 : 
Windows 11 est sorti. A mon avis, l'OS est maintenant assez mature pour que ça soit une bonne idée de passer de Windows 10 à 11, si votre PC est compatible.

Un guide d'installation de Windows 11 est disponible, pour les personnes intéressées, par ici :  [https://installerwindows.fr/](https://installerwindows.fr/)

Ce guide reste tout de même valable pour Windows 10.

## Table des matières

 - [**Sauvegarder ses données**](#sauvegarder-ses-données)
 - [**Création d'une clé USB de Windows**](#création-dune-clé-usb-de-windows)
 - [**Installation de Windows**](#installation-de-windows)
 - [**Tweaks regedit**](#tweaks-regedit)
 - [**Installation du driver vidéo**](#installation-du-driver-vidéo)
 - [**Installation des drivers**](#installation-des-drivers)
 - [**Mises à jour de Windows**](#mises-à-jour-de-windows)
 - [**Paramètres de Windows**](#paramètres-de-windows)
 - [**Réglages du panneau Nvidia**](#réglages-du-panneau-nvidia)
 - [**MSI Afterburner**](#msi-afterburner)
 - [**Mode MSI**](#mode-msi)
 - [**Mode de gestion d'alimentation**](#mode-de-gestion-dalimentation)
 - [**Installation des bibliothèques C++**](#installation-des-bibliothèques-c)
 - [**Les bonnes pratiques**](#les-bonnes-pratiques)
 
 
## Sauvegarder ses données
La première chose qu'on va faire pour s'assurer que tout fonctionne au mieux, c'est formater le PC et réinstaller Windows. Mais, en formatant le PC, **toutes les données du disque C: seront effacées**.

Sauvegarder ses données importantes, c'est une bonne idée.
Pour vous aider à faire ça de façon efficace, je vous ai préparé un document qui regroupe les méthodes de sauvegarde des logiciels les plus utilisés.

C'est par là : [https://github.com/Piwielle/Backup-logiciels/blob/main/README.md](https://github.com/Piwielle/Backup-logiciels/blob/main/README.md)
 
## Création d'une clé USB de Windows

La première étape, c'est de créer une clé USB d'installation de Windows, qu'on pourra utiliser pour formater un PC et réinstaller Windows proprement.

Il faut pour ça **une clé USB de 8 Go ou plus** et **accès à un PC sous Windows**.

- Télécharger l'outil de la catégorie "Création d'un support d'installation de Windows 10" sur [le site de Microsoft.](https://www.microsoft.com/fr-fr/software-download/windows10)
- Lancer l'outil, choisir ses paramètres et sa clé, puis lancer le processus.

La clé va ensuite se créer toute seule. L'opération peut prendre du temps selon la connexion, la clé USB, et le PC.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 1 - Créer une clé USB d'installation](https://www.youtube.com/watch?v=nidskw_JslQ).

Warning Cette vidéo concerne Windows 11, mais l'opération est identique pour Windows 10, il faut simplement télécharger l'outil pour windows 10 (lien au dessus).

## Installation de Windows

La clé étant créée, on va pouvoir l'utiliser pour formater le PC et installer une version fraîche de Windows.

Pour faire ça: 
- Mettre la clé dans un des ports USB, si sur un PC fixe préférablement directement sur un des ports à l'arrière, directement sur la carte mère.
- Démarrer le PC, et spammer la touche <kbd>F11</kbd> pendant le démarrage (des fois <kbd>F8</kbd> ou <kbd>F12</kbd>, selon la marque de la carte mère).
- Choisir la clé USB dans le menu de démarrage qui s'ouvre (en UEFI s'il y en a plusieurs).
- Se laisser guider par l'installateur de Windows.

> **Warning**
> 
> **Attention ! Lors du choix du lecteur sur lequel installer Windows, il faut être très attentif, c'est ici que vous allez formater vos disques. Si vous n'êtes pas très attentifs, vous allez perdre des données que vous vouliez garder !**

- Chaque SSD ou disque dur dans le PC correspond à un lecteur sur l'interface.
- Déterminer sur quel disque (lecteur) l'installation de Windows sera faite (on pourra s'aider de la taille pour les reconnaître).
- Supprimer toutes les partitions de ce que disque.
- Sélectionner l'espace non alloué représentant le disque, puis simplement appuyer sur suivant.

On pourra ensuite attendre la copie et l'installation de Windows. Pendant le compte à rebours de 10 secondes avant de redémarrer le PC, pensez à retirer la clé USB du PC. Ca évitera de redémarrer encore sur la clé et de recommencer l'installation en boucle.

Ensuite, on passe au réglage des paramètres initiaux avant de pouvoir accéder à Windows. On peut se laisser guider par l'installateur. Dites non à tout ce qu'il propose.

Support vidéo : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 2 - Installer Windows](https://youtu.be/5bPSazjZdSA)

> Cette vidéo présente l'installation de Windows 11. Le principe reste cependant quasiment identique pour Windows 10.

## Tweaks Regedit

Une fois que Windows sera installé, on se retrouve sur le bureau (avec une résolution très faible, ce qui est normal, la résolution normale viendra quand on aura installé les drivers de la carte graphique).
Je vous propose quelques petits tweaks basiques, qui vont légèrement améliorer les performances de votre PC, mais sans aucun problème de compatibilité, ou risque pour votre PC. La vidéo qui vous donnera des explications et du contexte est la suivante (recommandée).

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Quelques tweaks regedit (basiques)](https://www.youtube.com/watch?v=X4AVdnHFn_E)

Et la liste des tweaks proposés (à rentrer dans CMD en admin, encore une fois, et **attention, certaines des commandes sont sur deux lignes, prenez les en entier** !)

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Windows Search" /v AllowCortana /t REG_DWORD /d 00000000 /f`

`REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000000 /f`

`REG ADD "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v DisallowShaking /t REG_DWORD /d 00000001 /f`

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v SystemResponsiveness /t REG_DWORD /d 00000010 /f`

`REG ADD "HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer" /v DisableSearchBoxSuggestions /t REG_DWORD /d 00000001 /f`

`sc stop "SysMain" & sc config "SysMain" start=disabled`

`powercfg -h off`

`fsutil behavior set DisableDeleteNotify 0`



## Installation du driver vidéo
On va maintenant installer le driver vidéo de votre carte graphique. Pour ça, plusieurs méthodes selon vos besoins : 

**Carte AMD :**
Le pilote à télécharger sera disponible sur [https://www.amd.com/fr/support](https://www.amd.com/fr/support). Il suffit de choisir la bonne CG, de le télécharger, et de l'installer.

**Carte NVIDIA :**
Méthode 1 (à utiliser si vous avez besoin de Shadowplay, ou d'utiliser les hauts parleurs de votre écran, ou de Geforce experience, etc) : Le pilote à télécharger sera disponible sur [https://www.nvidia.fr/Download/Find.aspx?lang=fr](https://www.nvidia.fr/Download/Find.aspx?lang=fr) (sélectionner la version **DCH** -> faire la recherche -> télécharger le driver **Game Ready** le plus récent)
- Méthode 2 (à utiliser si vous souhaitez une version "lite" des drivers, qui n'a pas geforce experience, shadowplay, etc) : utiliser  [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/) pour installer votre driver.

Je discute des avantages et des inconvénients de NVCleanInstall dans cette vidéo (que je vous conseille encore une fois de regarder pour du contexte et des informations supplémentaires) : 

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Optimisation CG Nvidia @11:34](https://www.youtube.com/watch?v=eydeMfLlIsA&feature=youtu.be&t=694)

Une fois le driver vidéo installé, on aura (enfin) notre résolution normale.

## Installation des drivers
L'étape suivante consiste à installer les autres pilotes de votre système. La vidéo explicative est la suivante :

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Bien installer les pilotes de son PC](https://www.youtube.com/watch?v=LJ1tgPLHmG0)

Le résumé, c'est qu'utiliser des outils comme driverscloud, driverbooster, touslesdrivers, etc, c'est pas la meilleure façon d'installer vos drivers, et ça peut créer des soucis. Le site de la carte mère, et le site de la carte graphique sont les meilleurs endroits. Pour plus de détails, je vous renvoie à la vidéo.

## Mises à jour de Windows
Une fois tous nos drivers à jour, et avant d'entamer la suite des réglages de Windows, on va vérifier les éventuelles mises à jour. On le fait maintenant, parce que certaines grosses mises à jour peuvent réinitialiser certains paramètres de windows, ça nous évitera de faire les réglages 2 fois.
Il suffit d'aller dans les options de windows, cliquer sur windows update, et faire une recherche de mises à jour. Une fois qu'elles ont été téléchargées et installées, redémarrer le PC.
**Une fois le PC redémarré, refaites une vérification de mise à jour**. Des fois, le fait d'avoir fait une màj va débloquer l'installation d'autres màj, d'ou le fait de devoir faire la vérification deux fois de suite. Si il y a de nouvelles mises à jour, répéter l'opération, jusqu'à avoir windows à jour.

## Paramètres de Windows

Cette étape consiste simplement à se promener dans tous les paramètres de Windows, et lire et décocher ce qui ne vous semble pas utile. Pour vous aider, je peux vous proposer la vidéo suivante, qui va vous expliquer la majorité des paramètres que vous trouverez : 

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Paramètres Windows](https://www.youtube.com/watch?v=DP0e0xTk0Ck)


## Réglages du panneau Nvidia

Ensuite, je vous propose de faire un tour du panneau Nvidia, et d'activer et de désactiver certaines choses. Si vous avez une carte AMD, je peux pas vous aider, et je crois pas connaître de bon tuto pour. Profitez-en pour faire des expériences.

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Paramètres du panneau Nvidia](https://youtu.be/Z9pkHJGm004)

## MSI Afterburner
Msi Afterburner est un logiciel très léger et puissant, qui va vous permettre de :
- Gérer la vitesse des ventilos de votre CG, pour améliorer ses performances et/ou réduire son bruit.
- Regarder en temps réel l'utilisation de votre CG, sa température, ainsi que l'utilisation et températures de votre processeur, et du reste du PC.
- Overclock votre CG (sujet que je traiterai pas, car trop long et source d'instabilités).

Si une de ces fonctionnalités vous intéresse, vous pouvez l'installer. Sinon, c'est pas la peine.

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">Utiliser MSI Afterburner](https://youtu.be/eydeMfLlIsA?t=1)

## Mode MSI

Première note avant de continuer : Si vous avez une carte graphique AMD, le mode MSI est activé automatiquement à l'installation des pilotes, et vous n'avez rien à faire !

L'explication et l'utilité du mode MSI se trouvent dans la vidéo suivante : 

[<img src="https://i.imgur.com/cRUau5i.png" width="40" height="27">MSI Mode](https://youtu.be/eydeMfLlIsA?t=502)

Je vous rajoute ici le lien vers msi_util v3 : [http://www.mediafire.com/file/ewpy1p0rr132thk/MSI_util_v3.zip/file](http://www.mediafire.com/file/ewpy1p0rr132thk/MSI_util_v3.zip/file)

Si vous souhaitez des informations complémentaires sur le mode MSI (pour la culture générale), cette explication est très bien : [https://forum.malekal.com/viewtopic.php?t=62058](https://forum.malekal.com/viewtopic.php?t=62058)


## Mode de gestion d'alimentation
Un des réglages les plus importants que vous pouvez faire à votre système, c'est de changer son mode d'alimentation pour utiliser le mode le plus optimal pour les performances. Les réglages donnés ci dessous s'appliquent uniquement pour un PC fixe, pour un PC portable, je vous recommande de ne pas trop toucher, vous allez affecter l'autonomie du PC négativement.


/!\ Le mode de gestion d'alimentation le plus optimal pour les performances dépend de votre CPU.
- *CPU Intel 11XXX et plus anciens*: Les modes de gestion "**Hautes performances**" ou "**Performances optimales**" sont les meilleurs.
- *CPU Intel 12XXX et plus récents* : Le mode de gestion "**Hautes performances**" inclus dans Windows est le meilleur.
- *CPU AMD Ryzen 3XXX et plus anciens* : Le mode de gestion "**Ryzen balanced**" est le meilleur mode. (il s'installe quand vous installez les pilotes de chipset)
- *CPU AMD Ryzen 5XXX et plus récents* : Le mode de gestion "**Utilisation normale**" est le meilleur mode (vous pouvez bouger le slider dans Paramètres -> Système -> Alimentation pour un léger gain).

N'utilisez pas le mode "Performances optimales" sur un CPU récents (AMD 3XXX et plus récents, et Intel 12XXX et plus récents). Le mode de gestion d'alim "Performances optimales" date de 2017, et n'est pas optimal pour les architectures hybrides des processeurs récents.

## Installation des bibliothèques C++
Pour terminer, on va installer les bibliothèques C++. Ce sont des bibliothèques qui sont utilisées par énormément d'applications, qui refuseront de se lancer tant que vous ne les avez pas installé (teamspeak par exemple et énormément de jeux). Les erreurs "MSVCP100.dll" et beaucoup d'autres viennent de là.
Afin de les installer facilement, on va utiliser un pack qui les regroupe et les installe pour nous : [https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/)
- Allez sur le lien ci dessus, puis cliquer sur le bouton bleu à gauche de la page marqué "DOWNLOAD"
- Sur la page qui s'ouvre, cliquez sur n'importe quel drapeau pour lancer le téléchargement.
- Vous avez téléchargé une archive. Utilisez winRAR, ou 7-zip, ou le gestionnaire d'archive de windows pour extraire cette archive (clic droit -> extraire).
- Une fois l'archive extraite, ouvrez le dossier de l'archive extraite, faites un clic droit sur le fichier "**install_all**", et cliquez sur "**Lancer en tant qu'administrateur**".
- Attendre la fin des installations, puis redémarrer le PC.

## Les bonnes pratiques

L'installation de Windows est terminée, mais avant de vous laisser, on va parler des bonnes pratiques et des choses à faire sur le PC pour essayer de le garder propre le plus longtemps possible et éviter les problèmes.

- Eviter les optimisations. Malgré les promesses de gain de performances, d'input lag ou de stabilité, dans 99% des cas, il s'agit de bêtises qui vont vous flinguer Windows complètement, ou vous faire perdre des fonctionnalités pour ne rien gagner. Si ça vous amuse de bidouiller et que ça vous dérange pas de réinstaller Windows tous les mois, vous pouvez tenter l'aventure. Sauvegardez vos données, et soyez prêts à perdre du temps.
- Eviter les logiciels de nettoyage. Les Ccleaner, Iobit SystemCare, Glary utilities, DriversCloud, DriverBooster, etc etc, c'est des saloperies. Ils vendent du vent et ne vont rien faire de bien sur votre PC. Pour nettoyer les fichiers, le nettoyage de disque intégré à Windows est efficace et moins dangereux que ces outils.
- Garder son PC à jour. Ca inclut Windows, les applications, les jeux et tout ce qui est sur le PC. N'allez pas forcément installer toutes les mises à jour de tout dès le premier jour, mais une fois qu'une mise à jour de quelque chose a une semaine, vous pouvez l'installer sans problème.
- Essayez d'installer le moins d'applications possible. Pour garder un PC propre, installer une application seulement si vous en avez vraiment besoin. Dans la mesure du possible, utilisez les versions portables des applications, qui peuvent laisser moins de bordel sur le PC.
- Eviter les cracks. Essayez d'utiliser des alternatives gratuites, c'est souvent possible et bien moins dangereux. Le site [AlternativeTo](https://alternativeto.net/) peut vous aider à trouver des alternatives à un logiciel.
- Installez [uBlock Origin](https://ublockorigin.com/). Quel que soit votre navigateur, c'est essentiel d'avoir un bloqueur de pub efficace pour être tranquille sur internet. uBlock Origin est de loin le meilleur bloqueur de pub, et si vous en utilisez un autre, il est temps de le désinstaller et de changer.

Cette vidéo parle de la même chose, si vous préferez la version orale : [<img src="https://i.imgur.com/cRUau5i.png" height="20" width="30" alt="Logo YouTube" class="img-logo-ytb"> 9 - Les bonnes pratiques](https://youtu.be/SEdYm2gLgYk)
