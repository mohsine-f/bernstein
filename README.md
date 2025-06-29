# 🎼 Bernstein - Orchestration Kubernetes DevOps

---

## 📘 À propos

**Bernstein** est un projet DevOps visant à mettre en œuvre l'orchestration d’une application composée de plusieurs services conteneurisés, déployés sur un cluster Kubernetes multi-nœuds. Il s’inspire d’une architecture microservices basée sur une application de sondage.

L’objectif pédagogique principal est de **maîtriser les concepts d’orchestration, de déploiement, d’exposition et de supervision de services dans un cluster Kubernetes**, en s’appuyant sur des outils de production tels que Traefik et cAdvisor.

---

## 🧩 Composants de l’application

L’architecture repose sur **5 services applicatifs** et **3 outils d’infrastructure** :

### 🗳️ Services fonctionnels

| Service      | Description                                                                  |
| ------------ | ---------------------------------------------------------------------------- |
| **Poll**     | Application Flask qui collecte les votes et les envoie dans une queue Redis  |
| **Worker**   | Application Java qui consomme les votes dans Redis et les enregistre en base |
| **Result**   | Application Node.js qui affiche les résultats extraits de PostgreSQL         |
| **Redis**    | Base de données clé-valeur pour stocker les votes temporairement             |
| **Postgres** | Base de données relationnelle qui stocke les votes de manière persistente    |

### ⚙️ Infrastructure & réseau

| Outil                  | Rôle                                                                  |
| ---------------------- | --------------------------------------------------------------------- |
| **Traefik**            | Ingress Controller pour router les requêtes HTTP vers Poll/Result     |
| **cAdvisor**           | Monitoring des conteneurs déployés sur les nœuds                      |
| **ConfigMap & Secret** | Gestion centralisée de la configuration et des identifiants sensibles |

---

## 🛰️ Schéma d’architecture

![Screenshot 2025-06-21 112022](https://github.com/user-attachments/assets/507a3ef5-aceb-4070-bb81-ddad3e8361a2)

---

## 🧠 Enjeux pédagogiques

✅ Définir des fichiers YAML pour chaque ressource Kubernetes
✅ Appliquer les bonnes pratiques de configuration (limites, namespaces, labels, etc.)
✅ Gérer les secrets et les volumes persistants
✅ Exposer les services à l’aide d’un Ingress Controller (Traefik)
✅ Assurer une supervision des services avec cAdvisor
✅ Comprendre la répartition de charge et la tolérance aux pannes

---

## 👤 Auteur

Projet réalisé par [Mohsine Fajli](https://www.linkedin.com/in/mohsine-fajli) dans le cadre du module **Advanced DevOps - B-DOP-500**.
