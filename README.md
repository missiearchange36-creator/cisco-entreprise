# Architecture Réseau d'Entreprise Sécurisée (Cisco IOS)

Maquette réseau simulant une infrastructure d'entreprise segmentée en plusieurs VLANs avec accès sécurisé vers l'extérieur (Internet).

## 🗺️ Topologie du Réseau
![Topologie](topology.png)

## 📌 Fonctionnalités implémentées
- **Segmentation logique (VLANs) :**
  - VLAN 10 (Direction) : `192.168.100.0/24`
  - VLAN 20 (Employés) : `192.168.200.0/24`
- **Routage Inter-VLAN :** Configuration en Router-on-a-Stick via trunking 802.1Q.
- **Attribution dynamique (DHCP) :** Serveur DHCP centralisé avec relais d'adresses (`ip helper-address`) sur les sous-interfaces du routeur.
- **Accès WAN / Internet :** Route par défaut (`0.0.0.0/0`) et translation dynamique d'adresses **NAT/PAT (Overload)** filtrée par ACL.

## 🛠️ Dépannage & Notions techniques (Troubleshooting)
- **Adaptation matérielle (SFP / GLC-T) :** Utilisation d'un transceiver `GLC-T` pour convertir le port optique SFP natif du routeur Cisco 4300 en interface cuivre (RJ45).
- **Gestion des interfaces Cisco :** Distinction entre ports de commutation Couche 2 (`switchport`) et ports de routage Couche 3 (`no switchport` / interfaces IP dédiées).

## 📂 Fichiers du projet
- `architecture_cisco.pkt` : Topologie complète à ouvrir avec Cisco Packet Tracer (v8+)
- router_config.txt : montre la configuration du router
- switch_config.txt: montre la configuration du switch
