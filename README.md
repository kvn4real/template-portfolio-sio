# 🖥️ Template Portfolio BTS SIO SISR

> Template Portfolio statique développé en **HTML / CSS / JavaScript vanilla** dans le cadre du BTS SIO option SISR.

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Vercel](https://img.shields.io/badge/Déployé%20sur-Vercel-000000?style=flat&logo=vercel&logoColor=white)

---

## 📋 Sommaire

1. [Aperçu](#-aperçu)
2. [Prérequis](#-prérequis)
3. [Installation](#-installation)
4. [Configuration EmailJS](#-configuration-emailjs)
5. [Configuration Google Alerts](#-configuration-google-alerts)
6. [Déploiement sur Vercel](#-déploiement-sur-vercel)
7. [Structure du projet](#-structure-du-projet)
8. [Personnalisation](#-personnalisation)

---

## 👀 Aperçu

| Page | Rôle |
|------|------|
| `index.html` | Accueil — hero, compétences, stats animées |
| `projets.html` | Projets techniques avec modales et téléchargement de docs |
| `realisations.html` | Stages, compétences, certifications |
| `veille.html` | Flux RSS Google Alerts en temps réel |
| `contact.html` | Formulaire EmailJS + CV téléchargeable |
| `404.html` | Page d'erreur personnalisée |

**Fonctionnalités :**
- 🌙 Dark / Light mode persistant
- 🖱️ Curseur personnalisé
- 📡 Flux RSS Google Alerts (parser Atom XML)
- 📬 Formulaire de contact sans backend (EmailJS)
- ⚡ Animations au scroll
- 🔢 Compteurs animés
- 📱 Responsive mobile
- 🔍 SEO — meta, Open Graph, sitemap, robots.txt

---

## 🔧 Prérequis

Aucune dépendance à installer — le projet est 100% statique.

Tu auras besoin de :
- Un compte **[EmailJS](https://www.emailjs.com/)** (gratuit) pour le formulaire de contact
- Un compte **[Google](https://www.google.com/alerts)** pour les alertes RSS
- Un compte **[Vercel](https://vercel.com/)** pour l'hébergement (gratuit)

---

## 📥 Installation

### 1. Clone le repo

```bash
git clone https://github.com/VOTRE_GITHUB/VOTRE_REPO.git
cd VOTRE_REPO
```

### 2. Ouvre dans un éditeur

```bash
code .
```

### 3. Lance en local

Utilise l'extension **Live Server** sur VS Code ou simplement ouvre `index.html` dans ton navigateur.

> ⚠️ Les flux RSS et EmailJS nécessitent un serveur HTTP (pas `file://`). Utilise Live Server ou Vercel pour tester.

---

## 📬 Configuration EmailJS

### Étape 1 — Créer un compte
Va sur **[emailjs.com](https://www.emailjs.com/)** et crée un compte gratuit.

### Étape 2 — Ajouter un service email
- Va dans **"Email Services"** → **"Add New Service"**
- Choisis **Gmail** (ou autre)
- Connecte ton compte email
- Note ton **Service ID** (ex: `service_xxxxxxx`)

### Étape 3 — Créer un template
- Va dans **"Email Templates"** → **"Create New Template"**
- Passe en mode **Code Editor** (`</>`) et colle le fichier `emailjs_template.html` fourni
- Note ton **Template ID** (ex: `template_xxxxxxx`)

### Étape 4 — Récupérer ta clé publique
- Va dans **"Account"** → **"General"**
- Copie ta **Public Key**

### Étape 5 — Autoriser ton domaine
- Va dans **"Account"** → **"Security"** → **"Allowed Origins"**
- Ajoute `https://VOTRE_SITE.vercel.app`

### Étape 6 — Mettre à jour le code
Dans `contact.html`, remplace :

```js
const EJS_PUBLIC_KEY  = 'VOTRE_PUBLIC_KEY';
const EJS_SERVICE_ID  = 'VOTRE_SERVICE_ID';
const EJS_TEMPLATE_ID = 'VOTRE_TEMPLATE_ID';
```

---

## 📡 Configuration Google Alerts RSS

### Étape 1 — Créer une alerte
- Va sur **[google.com/alerts](https://www.google.com/alerts)**
- Saisis un mot-clé (ex: `CVE vulnerability`, `cyberattaque`, `zero-day`)
- Clique sur **"Afficher les options"**
- Livraison : choisis **"Flux RSS"**
- Clique **"Créer l'alerte"**

### Étape 2 — Récupérer le lien RSS
- Sur la page Google Alerts, clique sur l'icône **RSS** à côté de ton alerte
- Copie l'URL (format : `https://www.google.fr/alerts/feeds/XXXXXXX/XXXXXXX`)

### Étape 3 — Ajouter dans le code
Dans `veille.html`, remplace :

```js
const RSS_FEEDS = [
    { name: 'Google Alerts', url: 'VOTRE_LIEN_GOOGLE_ALERTS_1' },
    { name: 'Google Alerts', url: 'VOTRE_LIEN_GOOGLE_ALERTS_2' },
    // Ajoute autant de flux que tu veux
];
```

---

## 🚀 Déploiement sur Vercel

### Étape 1 — Push sur GitHub
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### Étape 2 — Importer sur Vercel
- Va sur **[vercel.com](https://vercel.com/)** → connecte-toi avec GitHub
- **"Add New Project"** → sélectionne ton repo
- Vercel détecte automatiquement que c'est un site statique
- Clique **"Deploy"** ✅

### Étape 3 — Domaine personnalisé (optionnel)
- Dans les settings du projet → **"Domains"**
- Ajoute ton domaine custom

> Le fichier `vercel.json` inclus gère automatiquement la redirection vers `404.html` pour les pages inexistantes.

---

## 📁 Structure du projet

```
/
├── index.html              # Page d'accueil
├── projets.html            # Projets techniques
├── realisations.html       # Stages & compétences
├── veille.html             # Veille technologique
├── contact.html            # Formulaire de contact
├── 404.html                # Page d'erreur
│
├── vercel.json             # Config Vercel (redirection 404)
├── robots.txt              # Instructions moteurs de recherche
├── sitemap.xml             # Plan du site (SEO)
│
├── favicon.ico             # Icône onglet navigateur
├── favicon.png             # Icône onglet (PNG)
│
├── CV_Votre_Nom.pdf        # Ton CV (à remplacer)
├── emailjs_template.html   # Template email (pour EmailJS)
│
└── doc_*.pdf               # Documentations projets (optionnel)
    ├── doc_vpn_ipsec.pdf
    ├── doc_nextcloud.pdf
    ├── doc_windows_server.pdf
    └── doc_apache.pdf
```

---

## 🎨 Personnalisation

### Informations personnelles
Recherche et remplace dans tous les fichiers :

| Placeholder | Remplacer par |
|-------------|---------------|
| `Votre Nom` | Ton nom complet |
| `votre.email@gmail.com` | Ton adresse email |
| `VOTRE_SITE.vercel.app` | Ton URL Vercel |
| `VOTRE_GITHUB` | Ton pseudo GitHub |
| `VOTRE_PROFIL` | Ton profil LinkedIn |
| `CV_Votre_Nom.pdf` | Le nom de ton CV |

### Couleurs
Dans chaque fichier HTML, modifie les variables CSS dans `:root` :

```css
:root {
    --accent: #00d4ff;   /* Couleur principale cyan */
    --bg: #080c10;       /* Fond sombre */
}
```

### Favicon
Remplace `favicon.ico` et `favicon.png` par ton propre logo (carré, minimum 64×64px).

---

## 📚 Technologies

| Technologie | Usage |
|-------------|-------|
| HTML5 / CSS3 / JS | Structure, style, interactions |
| [EmailJS](https://www.emailjs.com/) | Formulaire sans backend |
| [Google Alerts](https://www.google.com/alerts) | Flux RSS veille |
| [allorigins.win](https://allorigins.win/) | Proxy CORS pour les flux RSS |
| [Font Awesome 6](https://fontawesome.com/) | Icônes |
| [Google Fonts](https://fonts.google.com/) | Bebas Neue, Space Mono, DM Sans |
| [Vercel](https://vercel.com/) | Hébergement gratuit |

---

> Projet réalisé dans le cadre de l'épreuve E4 du **BTS SIO SISR**.
