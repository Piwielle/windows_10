# Optimiser son PC.
Il existe énormément de tweaks, optimisations, tutoriels, scripts et logiciels sur internet qui vont vous promettre de doubler vos FPS, réduire votre latence, stabiliser vos FPS, et je ne sais quoi d'autre. La majorité de ces tweaks sont faux, plus à jour, n'améliorent rien, et risquent de vous forcer à réinstaller windows en cas d'erreur (et des fois même si vous avez tout suivi correctement), voire même d'endommager votre PC.
Les simples tweaks que je vais détailler ici vont garantir un pc qui sera sain, et vous aurez fait 99% du chemin concernant l'optimisation de votre PC, sans danger pour le PC, et avec tout qui fonctionnera.

Si vous souhaitez gratter le 1% restant, faites le, mais sachez que c'est à vos risques et périls, que vous allez forcément à un moment faire une connerie et devoir réinstaller windows, et le tout pour un gain de performances qui sera très très faible (globalement invisible). <br/>

Voici ce que je vous conseille sur une nouvelle installation de windows. Ce sont des tweaks qui sont sans dangers pour le pc, que ce soit niveau hardware ou software. Si vous avez une question particulière durant une des étapes, n'hésitez pas à demander sur *[`Discord`](https://discord.gg/Pw8BC6T)* !<br/>

## Table des matières

 - [**Installation de Windows**](#windows-install)
 - [**Désactivation des drivers automatiques**](#drivers-auto)
 - [**Tweaks regedit**](#regedit)
 - [**Installation du driver vidéo**](#driver-nvidia)
 - [**Installation des drivers**](#drivers)
 - [**Mises à jour de Windows**](#windows-maj)
 - [**Paramètres de Windows**](#windows-settings)
 - [**W10Privacy**](#w10privacy)
 - [**Réglages du panneau Nvidia**](#panneau-nvidia)
 - [**MSI Afterburner**](#afterburner)
 - [**Mode MSI**](#msi-mode)
 - [**ISLC : Intelligent Standby List Cleaner**](#islc)
 - [**Mode de gestion d'alimentation**](#alimentation)
## Installation de Windows

**Note:** Je recommande de réinstaller Windows, afin de repartir sur une base saine. Qui sait ce que vous avez installé sur votre PC, quels tweaks (utiles ou non) vous avez pu installer, quels logiciels inutiles ou virus vous pouvez avoir sur votre PC, etc etc. Réinstaller complètement Windows permettra de raptir complètement d'une base sain, et d'assurer des performances et une compatibilité maximale.

Pour installer Windows, je vous propose la vidéo de Topachat, qui est complète et couvre bien le sujet. 

[**https://www.youtube.com/watch?v=uHOP4UbEGug**](https://www.youtube.com/watch?v=uHOP4UbEGug)

La seule chose que j'ajouterai, c'est que je vous suggère de **débrancher le câble Ethernet (ou la carte wifi) pendant l'installation de Windows.** En effet, Windows par défault installe des drivers pour votre matériel, pendant l'installation de Windows. Je considère ça comme pas idéal, parce que la première chose qu'un va faire après l'install, c'est de mettre à jour nos drivers, alors autant s'épargner l'installation d'anciennes versions de drivers par Windows.
On pourra rebrancher le câble ethernet uniquement **après avoir désactivé l'installation automatique des drivers**

## Désactivation des drivers automatiques & Tweaks Regedit

Une fois que Windows sera installé, on se retrouve sur le bureau (avec une résolution très faible, ce qui est normal, la résolution normale viendra quand on aura installé les drivers de la carte graphique).
La première chose qu'on va faire, c'est désactiver l'installation automatique des drivers de Windows. Pour ce faire, je vous propose de suivre la vidéo suivante : 

[**https://www.youtube.com/watch?v=IMmNS6yAK4g**](https://www.youtube.com/watch?v=IMmNS6yAK4g)

Si vous n'avez pas envie de regarder la vidéo, la commande à rentrer dans CMD (en admin) est la suivante (ceci dit, je vous conseille quand même la vidéo, qui vous donnera plus d'explications, et de contexte)

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\DriverSearching" /v SearchOrderConfig /t REG_DWORD /d 00000000 /f`

Tant qu'on est à faire des changements dans regedit, je vous propose quelques petits tweaks basiques, qui vont légèrement améliorer les performances de votre PC, mais sans aucun problème de compatibilité, ou risque pour votre PC. La vidéo qui vous donnera des explications et du contexte est la suivante (recommandée).

[**https://www.youtube.com/watch?v=X4AVdnHFn_E**](https://www.youtube.com/watch?v=X4AVdnHFn_E)

Et la liste des tweaks proposés (à rentrer dans CMD en admin, encore une fois)

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Windows Search" /v AllowCortana /t REG_DWORD /d 00000000 /f`

`REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000000 /f`

`REG ADD "HKCU\Keyboard Layout\toggle" /v "Language Hotkey" /t REG_SZ /d 3 /f`

`REG ADD "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v DisallowShaking /t REG_DWORD /d 00000001 /f
powercfg -h off`

`fsutil behavior set DisableDeleteNotify 0`

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v SystemResponsiveness /t REG_DWORD /d 00000010 /f`

Une fois les drivers de Windows désactivés, vous devez impérativement **redémarrer le PC**. Une fois que c'est fait, vous pouvez **rebrancher internet**

## Installation du driver vidéo
On va maintenant installer le driver vidéo de votre carte graphique. Pour ça, plusieurs méthodes selon vos besoins : 

**Carte AMD :**
Le pilote à télécharger sera disponible sur `https://www.amd.com/fr/support`. Il suffit de choisir la bonne CG, de le télécharger, et de l'installer.

**Carte NVIDIA :**
Méthode 1 (à utiliser si vous avez besoin de Shadowplay, ou d'utiliser les hauts parleurs de votre écran, ou de Geforce experience, etc) : Le pilote à télécharger sera disponible sur `https://www.nvidia.fr/Download/Find.aspx?lang=fr` (sélectionner la version **STANDARD** -> faire la recherche -> télécharger le driver **Game Ready** le plus récent)
- Méthode 2 (à utiliser si vous souhiatez une version "lite" des drivers, qui n'a pas geforce experience, shadowplay, etc) : utiliser * [`NVCleanInstall`](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)* pour installer votre driver.

Je discute des avantages et des inconvénients de NVCleanInstall dans cette vidéo (que je vous conseille encore une fois de regarder pour du contexte et des informations supplémentaires) : 

[`Optimisation CG Nvidia @11:34`]https://www.youtube.com/watch?v=eydeMfLlIsA&feature=youtu.be&t=694

Une fois le driver vidéo installé, on aura (enfin) notre résolution choisie

## Installation des drivers
L'étape suivante consiste à installer les autres pilotes de votre système.
