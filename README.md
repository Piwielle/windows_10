
# Optimiser son PC.
Il existe énormément de tweaks, optimisations, tutoriels, scripts et logiciels sur internet qui vont vous promettre de doubler vos FPS, réduire votre latence, stabiliser vos FPS, et je ne sais quoi d'autre. La majorité de ces tweaks sont faux, plus à jour, n'améliorent rien, et risquent de vous forcer à réinstaller windows en cas d'erreur (et des fois même si vous avez tout suivi correctement), voire même d'endommager votre PC.
Les simples tweaks que je vais détailler ici vont garantir un pc qui sera sain, et vous aurez fait 99% du chemin concernant l'optimisation de votre PC, sans danger pour le PC, et avec tout qui fonctionnera.

Si vous souhaitez gratter le 1% restant, faites le, mais sachez que c'est à vos risques et périls, que vous allez forcément à un moment faire une connerie et devoir réinstaller windows, et le tout pour un gain de performances qui sera très très faible (globalement invisible). <br/>

Voici ce que je vous conseille sur une nouvelle installation de windows. Ce sont des tweaks qui sont sans dangers pour le pc, que ce soit niveau hardware ou software. Si vous avez une question particulière durant une des étapes, n'hésitez pas à demander sur *[`Discord`](https://discord.gg/Pw8BC6T)* !<br/>

## Table des matières

 - [**Installation de Windows**](#Installation-de-Windows)
 - [**Désactivation des drivers automatiques**](#Désactivation-des-drivers-automatiques)
 - [**Tweaks regedit**](#Tweaks-regedit)
 - [**Installation du driver vidéo**](#Installation-du-driver-vidéo)
 - [**Installation des drivers**](#Installation-des-drivers)
 - [**Mises à jour de Windows**](#Mises-à-jour-de-Windows)
 - [**Paramètres de Windows**](#Paramètres-de-Windows)
 - [**W10Privacy**](#w10privacy)
 - [**Réglages du panneau Nvidia**](#Réglages-du-panneau-Nvidia)
 - [**MSI Afterburner**](#MSI-Afterburner)
 - [**Mode MSI**](#Mode-MSI)
 - [**ISLC Intelligent Standby List Cleaner**](#ISLC-Intelligent-Standby-List-Cleaner)
 - [**Mode de gestion d'alimentation**](#Mode-de-gestion-dalimentation)
## Installation de Windows

**Note:** Je recommande de réinstaller Windows, afin de repartir sur une base saine. Qui sait ce que vous avez installé sur votre PC, quels tweaks (utiles ou non) vous avez pu installer, quels logiciels inutiles ou virus vous pouvez avoir sur votre PC, etc etc. Réinstaller complètement Windows permettra de repartir complètement d'une base saine, et d'assurer des performances et une compatibilité maximale.

Pour installer Windows, je vous propose la vidéo de Topachat, qui est complète et couvre bien le sujet. 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`[TUTO] Installer Windows 10 & Tes Drivers - TopAchat [FR]`](https://www.youtube.com/watch?v=uHOP4UbEGug)

La seule chose que j'ajouterai, c'est que je vous suggère de **débrancher le câble Ethernet (ou la carte wifi) pendant l'installation de Windows.** En effet, Windows par défaut installe des drivers pour votre matériel, pendant l'installation de Windows. Je considère ça comme pas idéal, parce que la première chose qu'on va faire après l'install, c'est de mettre à jour nos drivers, alors autant s'épargner l'installation d'anciennes versions de drivers par Windows.
On pourra rebrancher le câble ethernet uniquement **après avoir désactivé l'installation automatique des drivers**.

## Désactivation des drivers automatiques & Tweaks Regedit

Une fois que Windows sera installé, on se retrouve sur le bureau (avec une résolution très faible, ce qui est normal, la résolution normale viendra quand on aura installé les drivers de la carte graphique).
La première chose qu'on va faire, c'est désactiver l'installation automatique des drivers de Windows. Pour ce faire, je vous propose de suivre la vidéo suivante : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Désactiver l'installation automatique des drivers de Windows Update`](https://www.youtube.com/watch?v=IMmNS6yAK4g)

Si vous n'avez pas envie de regarder la vidéo, la commande à rentrer dans CMD (en admin) est la suivante (ceci dit, je vous conseille quand même la vidéo, qui vous donnera plus d'explications, et de contexte)

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\DriverSearching" /v SearchOrderConfig /t REG_DWORD /d 00000000 /f`

Tant qu'on est à faire des changements dans regedit, je vous propose quelques petits tweaks basiques, qui vont légèrement améliorer les performances de votre PC, mais sans aucun problème de compatibilité, ou risque pour votre PC. La vidéo qui vous donnera des explications et du contexte est la suivante (recommandée).

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Quelques tweaks regedit (basiques)`](https://www.youtube.com/watch?v=X4AVdnHFn_E)

Et la liste des tweaks proposés (à rentrer dans CMD en admin, encore une fois)

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Windows Search" /v AllowCortana /t REG_DWORD /d 00000000 /f`

`REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 00000000 /f`

`REG ADD "HKCU\Keyboard Layout\toggle" /v "Language Hotkey" /t REG_SZ /d 3 /f`

`REG ADD "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v DisallowShaking /t REG_DWORD /d 00000001 /f`

`powercfg -h off`

`fsutil behavior set DisableDeleteNotify 0`

`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v SystemResponsiveness /t REG_DWORD /d 00000010 /f`

Une fois les drivers de Windows désactivés, vous devez impérativement **redémarrer le PC**. Une fois que c'est fait, vous pouvez **rebrancher internet**

## Installation du driver vidéo
On va maintenant installer le driver vidéo de votre carte graphique. Pour ça, plusieurs méthodes selon vos besoins : 

**Carte AMD :**
Le pilote à télécharger sera disponible sur `https://www.amd.com/fr/support`. Il suffit de choisir la bonne CG, de le télécharger, et de l'installer.

**Carte NVIDIA :**
Méthode 1 (à utiliser si vous avez besoin de Shadowplay, ou d'utiliser les hauts parleurs de votre écran, ou de Geforce experience, etc) : Le pilote à télécharger sera disponible sur `https://www.nvidia.fr/Download/Find.aspx?lang=fr` (sélectionner la version **STANDARD** -> faire la recherche -> télécharger le driver **Game Ready** le plus récent)
- Méthode 2 (à utiliser si vous souhaitez une version "lite" des drivers, qui n'a pas geforce experience, shadowplay, etc) : utiliser  [`NVCleanInstall`](https://www.techpowerup.com/download/techpowerup-nvcleanstall/) pour installer votre driver.

Je discute des avantages et des inconvénients de NVCleanInstall dans cette vidéo (que je vous conseille encore une fois de regarder pour du contexte et des informations supplémentaires) : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Optimisation CG Nvidia @11:34`](https://www.youtube.com/watch?v=eydeMfLlIsA&feature=youtu.be&t=694)

Une fois le driver vidéo installé, on aura (enfin) notre résolution normale.

## Installation des drivers
L'étape suivante consiste à installer les autres pilotes de votre système. La vidéo explicative est la suivante :

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Installer ses drivers de la bonne façon`](https://www.youtube.com/watch?v=TzSJ_DTLfqY)

Le résumé, c'est qu'utiliser des outils comme driverscloud, driverbooster, touslesdrivers, etc, c'est pas la meilleure façon d'installer vos drivers, et ça peut créer des soucis. Le site de la carte mère, et le site de la carte graphique sont les meilleurs endroits. Pour plus de détails, je vous renvoie à la vidéo.

## Mises à jour de Windows
Une fois tous nos drivers à jour, et avant d'entamer la suite des réglages de Windows, on va vérifier les éventuelles mises à jour. On le fait maintenant, parce que certaines grosses mises à jour peuvent réinitialiser certains paramètres de windows, ça nous évitera de faire les réglages 2 fois.
Il suffit d'aller dans les options de windows, cliquer sur windows update, et faire une recherche de mises à jour. Une fois qu'elles ont été téléchargées et installées, redémarrer le PC.
**Une fois le PC redémarré, refaites une vérification de mise à jour**. Des fois, le fait d'avoir fait une màj va débloquer l'installation d'autres màj, d'ou le fait de devoir faire la vérification deux fois de suite. Si il y a de nouvelles mises à jour, répéter l'opération, jusqu'à avoir windows à jour.

## Paramètres de Windows

Cette étape consiste simplement à se promener dans tous les paramètres de Windows, et lire et décocher ce qui ne vous semble pas utile. Pour vous aider, je peux vous proposer la vidéo suivante, qui va vous expliquer la majorité des paramètres que vous trouverez : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Paramètres Windows`](https://www.youtube.com/watch?v=DP0e0xTk0Ck)

## W10Privacy

W10privacy est le logiciel que j'utilise pour régler certains paramètres pas directement accessibles dans les réglages de windows. J'ai choisi celui ci pour la clarté des explications qu'il propose, et la possibilité de simplement revenir en arrière sur un changement.
Vidéo explicative ici (conseillée) : 


![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`W10Privacy (et autres logiciels de "vie privée")`](https://www.youtube.com/watch?v=oPUJThkVmXI)

## Réglages du panneau Nvidia

Ensuite, je vous propose de faire un tour du panneau Nvidia, et d'activer et de désactiver certaines choses. Si vous avez une carte AMD, je peux pas vous aider, et je crois pas connaître de bon tuto pour. Profitez-en pour faire des expériences.

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Paramètres du panneau Nvidia`](https://youtu.be/Z9pkHJGm004)

## MSI Afterburner
Msi Afterburner est un logiciel très léger et puissant, qui va vous permettre de :
- gérer la vitesse des ventilos de votre CG, pour améliorer ses performances et/ou réduire son bruit
- regarder en temps réel l'utilisation de votre CG, sa température, ainsi que l'utilisation et températures de votre processeur, et du reste du PC.
- overclock votre CG (sujet que je traiterai pas, car trop long et source de potentielle instabilité)

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Utiliser MSI Afterburner`](https://youtu.be/eydeMfLlIsA?t=1)

## Mode MSI
L'explication et l'utilité du mode MSI se trouvent dans la vidéo suivante : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`MSI Mode`](https://youtu.be/eydeMfLlIsA?t=502)

Je vous rajoute ici le lien vers msi_util v2 : [http://www.mediafire.com/file/2kkkvko7e75opce/MSI_util_v2.zip](http://www.mediafire.com/file/2kkkvko7e75opce/MSI_util_v2.zip)

Si vous souhaitez des informations complémentaires sur le mode MSI (pour la culture générale), cette explication est très bien : [https://forum.malekal.com/viewtopic.php?t=62058](https://forum.malekal.com/viewtopic.php?t=62058)

## ISLC Intelligent Standby List Cleaner
Comme MSI Afterburner, j'utilise ISLC sur tous mes ordinateurs, pour sa légèreté, et les deux fonctionnalités utiles qu'il propose : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`ISLC`](https://youtu.be/QV8IojCtoOQ)

## Mode de gestion d'alimentation
Pour finir, un des réglages les plus importants que vous pouvez faire à votre système, c'est de changer son mode d'alimentation pour le passer en "hautes performances". Une vidéo explicative si vous en avez besoin est disponible ici : 

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) [`Mode de gestion d'alimentation`](https://youtu.be/SAlqNxr1eVY)
