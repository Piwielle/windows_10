# **Piwi at discord**
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
*[`https://www.youtube.com/watch?v=uHOP4UbEGug`](https://www.youtube.com/watch?v=uHOP4UbEGug)*

La seule chose que j'ajouterai, c'est que je vous suggère de **débrancher le câble Ethernet (ou la carte wifi) pendant l'installation de Windows.** En effet, Windows par défault installe des drivers pour votre matériel, pendant l'installation de Windows. Je considère ça comme pas idéal, parce que la première chose qu'un va faire après l'install, c'est de mettre à jour nos drivers, alors autant s'épargner l'installation d'anciennes versions de drivers par Windows.
On pourra rebrancher le câble ethernet uniquement **après avoir désactivé l'installation automatique des drivers**

## Désactivation des drivers automatiques

Une fois que Windows sera installé, on se retrouve sur le bureau (avec une résolution très faible, ce qui est normal, la résolution normale viendra quand on aura installé les drivers de la carte graphique).
La première chose qu'on va faire, c'est désactiver l'installation automatique des drivers de Windows. Pour ce faire, je vous propose de suivre la vidéo suivante : 
*[`https://www.youtube.com/watch?v=IMmNS6yAK4g`](https://www.youtube.com/watch?v=IMmNS6yAK4g)*

Si vous n'avez pas envie de regarder la vidéo, la commande à rentrer dans CMD (en admin) est la suivante (ceci dit, je vous conseille quand même la vidéo, qui vous donnera plus d'explications, et de contexte)
`REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\DriverSearching" /v SearchOrderConfig /t REG_DWORD /d 00000000 /f`
