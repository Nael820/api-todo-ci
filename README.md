# API TODO - CI/CD Multi-Environnements

[![Deploy Multi-Env](https://github.com/Nael820/api-todo-ci/actions/workflows/deploy-multi-env.yml/badge.svg)](https://github.com/Nael820/api-todo-ci/actions/workflows/deploy-multi-env.yml)
![Node](https://img.shields.io/badge/node-18.x-green)

API TODO avec pipeline CI/CD professionnel et déploiement multi-environnements.

---

## 🌍 Environnements Déployés

| Environnement | URL | Branche | Status |
|---------------|-----|---------|--------|
| **Production** | [api-todo-nael-prod.onrender.com](https://api-todo-nael-prod.onrender.com) | `main` | ✅ Actif |
| **Staging** | [api-todo-nael-staging.onrender.com](https://api-todo-nael-staging.onrender.com) | `develop` | ✅ Actif |

---

## 🚀 Workflow de Déploiement

**Sur `develop` (Staging)** :
1. Tests unitaires
2. Déploiement automatique sur Staging
3. Health check automatique

**Sur `main` (Production)** :
1. Tests unitaires
2. Création tag version (v1.0.x)
3. Déploiement automatique sur Production
4. Health check automatique
5. Push du tag vers GitHub

---

## 📡 Endpoints API

| Méthode | Route | Description |
|---------|-------|-------------|
| GET | `/` | Infos de l'API |
| GET | `/todos` | Liste tous les todos |
| GET | `/todos/:id` | Un todo spécifique |
| POST | `/todos` | Créer un todo |
| PUT | `/todos/:id` | Modifier un todo |
| DELETE | `/todos/:id` | Supprimer un todo |
| GET | `/health` | Health check |

---

## 🧪 Tests
```bash
# Installer les dépendances
npm install

# Lancer les tests
npm test
```

**Coverage actuel : 8 tests passent**

---

## ⚙️ Pipeline CI/CD

Le pipeline s'exécute automatiquement sur chaque push.

### Jobs exécutés

- **Tests** : Vérifie que tous les tests passent
- **Deploy Staging** : Déploie automatiquement sur staging (branche develop)
- **Deploy Production** : Déploie sur production avec création de tag (branche main)

---

## ✅ Bonnes Pratiques Appliquées

- **Branches protégées** : Impossible de push directement sur `main`
- **Tests automatiques** : Aucun déploiement sans tests verts
- **Environnements séparés** : Staging pour tester, Production pour users
- **Versioning automatique** : Tags créés à chaque déploiement production
- **Health checks** : Vérification automatique après déploiement
- **Secrets management** : Clés API dans GitHub Secrets

---

## 💻 Configuration Locale
```bash
# Cloner le repository
git clone https://github.com/Nael820/api-todo-ci.git
cd api-todo-ci

# Installer les dépendances
npm install

# Lancer en développement
npm start

# Lancer les tests
npm test
```

L'API sera accessible sur `http://localhost:3000`

---

## 🔧 Variables d'Environnement

| Variable | Staging | Production |
|----------|---------|------------|
| `NODE_ENV` | `staging` | `production` |
| `PORT` | Auto (Render) | Auto (Render) |

---

## 📚 Projet réalisé dans le cadre du cours CI/CD

**MyDigitalSchool - Février 2026**

### Technologies utilisées
- Node.js 18.x
- Express 4.x
- Jest 29.x
- GitHub Actions
- Render.com

### Auteur
**Nael** - [GitHub](https://github.com/Nael820)