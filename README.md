# 📘 **SAE R502 – Piloter un Projet Informatique (Marionnet)**
**Conception, configuration et pilotage d’une architecture réseau sous Marionnet**

# **1. Présentation générale du projet**

Ce projet s’inscrit dans le cadre de la **SAE R502 – Piloter un Projet Informatique**, au sein du **BUT Réseaux & Télécommunications – Parcours Cybersécurité**.
L’objectif est de **concevoir, mettre en œuvre et documenter une infrastructure réseau complète**, tout en appliquant une **méthode Agile** pour structurer le travail en équipe.

Le projet se déroule entièrement sous **Marionnet**, solution d’émulation réseau légère et adaptée aux environnements pédagogiques.

Il mobilise des notions essentielles du métier d’administrateur réseau :

* création d’une topologie multi-machines ;
* configuration avancée de VLAN ;
* routage statique ;
* services réseau (DHCP) ;
* sécurisation via pare-feu (iptables) ;
* automatisation des services système ;
* documentation et gestion de version (Git).

# **2. Équipe projet**

Projet réalisé en binôme :

* **Lahoucine El Merabet**
* **Keyane Lhamzi**

Encadrement :
**IUT de Villetaneuse – Université Sorbonne Paris Nord**

# **3. Organisation et gestion de projet (Agile – Scrum)**

Nous avons appliqué une organisation inspirée de Scrum, adaptée au format SAE :

* **Backlog complet** recensant l’ensemble des tâches techniques et organisationnelles ;
* **Trello** pour le suivi visuel des tâches (To Do, Doing, Done) ;
* **Découpage en sprints hebdomadaires** ;
* **Versions livrées à chaque étape (V1 → V4)** ;
* **Commits réguliers** pour assurer la traçabilité.

### Découpage en sprints

| Sprint       | Période          | Objectif principal                          |
| ------------ | ---------------- | ------------------------------------------- |
| **Sprint 1** | 17–24 novembre   | Topologie + VLAN + organisation Agile       |
| **Sprint 2** | 24 nov. – 1 déc. | DHCP, routage et connectivité               |
| **Sprint 3** | 1–8 décembre     | Sécurisation (iptables) + améliorations     |
| **Sprint 4** | 8–11 décembre    | Automatisation + documentation + soutenance |


# **4. Architecture réseau – Conception finale**

L’architecture finale repose sur :

### **12 machines clientes**

* M1 à M6
* MA à MF

### **3 switchs interconnectés**

* SW1, SW2, SW3
  → Liaisons configurées en mode **trunk**

### **3 équipements réseau majeurs**

* Un **serveur DHCP**
* Un **pare-feu** (iptables)
* Une **Gateway** (passerelle réseau)

### **Répartition VLAN**

| VLAN        | Machines associées     | Usage    |
| ----------- | ---------------------- | -------- |
| **VLAN 10** | M1, M2, M3, M4, M5, M6 | Réseau 1 |
| **VLAN 20** | MA, MB, MC, MD, ME, MF | Réseau 2 |

### **Objectifs atteints**

* Isolation logique entre réseaux
* Propagation des VLAN via trunks
* Connectivité maîtrisée entre les sous-réseaux
* Sécurisation des flux via firewall

# **5. Fonctionnalités implantées**

## **Version 1 – Topologie & VLAN**

* Construction complète du réseau Marionnet
* Nomination de tous les équipements
* Configuration de tous les VLAN (10 et 20)
* Mise en place des trunks
* Câblage logique final
* Livrable : **V1**

## **Version 2 – DHCP & routage**

* Définition du plan d’adressage IP
* Mise en place du serveur DHCP (ISC-DHCP)
* Configuration des pools pour chaque VLAN
* Configuration du routage statique
* Test complet de la distribution IP
* Livrable : **V2**

## **Version 3 – Pare-feu (iptables) & stabilité**

* Définition d’une politique de filtrage **DROP par défaut**
* Autorisation des flux essentiels (DHCP, ICMP…)
* Blocage des ports sensibles
* Amélioration des options DHCP
* Tests de sécurité sur l’ensemble des machines
* Livrable : **V3**

## **Version 4 – Automatisation des services**

* Configuration du service **Networking** sur Debian
  → lancement automatique de la requête DHCP au démarrage
* Suppression des contraintes de configuration manuelle
* Stabilisation de la topologie pour la soutenance
* Livrable : **V4**

# **6. Tests & validation**

Nous avons validé la cohérence de l’infrastructure grâce à une série de tests :

### VLAN

* Vérification de l’isolement
* Test des trunks SW1 ↔ SW2 ↔ SW3

### DHCP

* Attribution automatique sur tous les clients
* Test des renouvellements de bail
* Cohérence des sous-réseaux

### Routage

* Communication inter-réseaux via firewall
* Tests de reachability (ping, traceroute)

### Firewall

* Validation des ports autorisés
* Vérification du blocage des flux interdits

### Automatisation

* Tests post-redémarrage : réseau pleinement fonctionnel sans intervention manuelle


# **7. Structure du dépôt GitHub**

```
/marionnet_project     → Fichiers .mar (V1 → V4)
/docs               → Planning, Backlog, diaporama 
README.md              → Documentation principale
```

# **8. Planning global**

Le planning détaillé (par sprint, par tâche, par membre du binôme) est disponible dans :
📁 `/docs/Planning détaillé du projet – SAE R502 _ Piloter un Projet Informatique.pdf`

Il contient :

* la répartition des tâches entre **Lahoucine El Merabet** et **Keyane Lhamzi**,
* les objectifs hebdomadaires,
* les livrables produits par version.


# **9. Ressources utiles**

* **Trello du projet**
  [https://trello.com/invite/b/69137cc0c72c7519468f0a30/ATTI39368d6616d92829a56b9d08e44afc1aCB427B90/kanban-sae-r502-piloter-un-projet-informatique](https://trello.com/invite/b/69137cc0c72c7519468f0a30/ATTI39368d6616d92829a56b9d08e44afc1aCB427B90/kanban-sae-r502-piloter-un-projet-informatique)

* **IUT de Villetaneuse – Université Sorbonne Paris Nord**

