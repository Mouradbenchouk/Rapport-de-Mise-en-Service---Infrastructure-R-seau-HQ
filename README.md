# Projet Configuration Réseau - Zone HQ (Siège)

## Description
Ce projet simule une architecture réseau d'entreprise hautement disponible. L'objectif est de garantir une connectivité ininterrompue pour les utilisateurs (VLAN 10) et les serveurs (VLAN 20) via la redondance des équipements de cœur de réseau et des liens physiques.

## Architecture & Technologies
- **Topologie :** Modèle hiérarchique (Cœur / Accès).
- **Redondance L2 :** EtherChannel (LACP) entre les switches Core pour augmenter la bande passante.
- **Gestion des VLANs :** VTP (VLAN Trunking Protocol) pour la synchronisation automatique.
- **Redondance L3 :** HSRP (Hot Standby Router Protocol) pour la passerelle par défaut virtuelle.
- **Routage :** Routage Inter-VLAN activé sur switches multicouches (3650).

## Tâches Réalisées
1. **Sécurisation :** Configuration des noms d'hôtes, mots de passe enable, et accès console/VTY.
2. **Agrégation :** Mise en place d'un EtherChannel LACP entre Core-01 et Core-02.
3. **Segmentation :** Configuration du VTP (Serveur/Client) et propagation des VLANs.
4. **Haute Disponibilité :** Configuration du HSRP sur les interfaces SVI pour la redondance des passerelles.
5. **Connectivité :** Adressage IP statique des PC et du Serveur avec routage actif.

## Schéma d'Adressage (Extraits)
- **VLAN 10 (Utilisateurs) :** 10.0.10.0/24 (VIP HSRP: 10.0.10.254)
- **VLAN 20 (Serveurs) :** 10.0.20.0/24 (VIP HSRP: 10.0.20.254)
