# Sandbox_CapeV2
Étude et mise en place d’une sandbox pour l’analyse dynamique de malwares

# CAPEv2 Sandbox – Étude et mise en place

## Objectif
Ce projet présente la mise en place et l’étude d’une sandbox **CAPEv2** dédiée à l’analyse dynamique de malwares.
L’objectif est de comprendre l’architecture, la configuration et le fonctionnement d’une sandbox moderne utilisée en contexte SOC.

## Présentation de CAPE
CAPEv2 est une solution open-source dérivée de Cuckoo Sandbox.
Elle permet d’exécuter automatiquement des fichiers suspects dans des machines virtuelles isolées afin d’observer leur comportement :
création de processus, modifications système, accès registre, trafic réseau, dumps mémoire, captures d’écran, etc.

## Architecture
L’architecture repose sur deux composants principaux :

- **Host (Linux)**  
  Machine hôte exécutant CAPE, gérant l’orchestration des analyses, la virtualisation et la génération des rapports.

- **Guest (Windows)**  
  Machine virtuelle isolée utilisée pour exécuter les échantillons, restaurée à partir d’un snapshot propre à chaque analyse.

La communication Host ↔ Guest s’effectue via un réseau virtuel isolé afin de limiter tout risque.

## Environnement technique
- Hyperviseur : **KVM**
- Gestion des VM : **virt-manager**
- Sandbox : **CAPEv2**
- Langage : **Python (Poetry)**
- OS Host : Linux
- OS Guest : Windows

## Travail réalisé
- Installation et configuration de CAPEv2
- Mise en place d’un réseau virtuel isolé
- Création et préparation d’une VM d’analyse
- Installation et configuration de l’agent CAPE
- Configuration des fichiers principaux :
  - `cuckoo.conf`
  - `routing.conf`
  - `kvm.conf`
- Lancement du serveur web CAPE
- Réalisation de premières analyses
- Rédaction d’un rapport technique détaillé

## Rapport
Le rapport complet décrivant l’ensemble des étapes, choix techniques et analyses est disponible dans le dossier **/docs**.

## Compétences mises en œuvre
- Virtualisation et isolation
- Analyse comportementale de malwares
- Lecture et interprétation de logs système et réseau
- Documentation technique


## Avertissement
Aucun échantillon malveillant, dump mémoire ou capture réseau réelle n’est inclus dans ce dépôt.
Ce projet est destiné à un usage **pédagogique uniquement**.
