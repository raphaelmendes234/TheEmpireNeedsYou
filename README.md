# TheEmpireNeedsYou - Test Technique Alternance Merci Creative

Ce projet a été réalisé dans le cadre d’un test technique pour le poste de Développeur en alternance chez Merci Creative.  
L’objectif : créer une **landing page responsive, moderne et immersive** pour recruter de nouveaux adeptes du Côté Obscur.

Le but étant de créer une landing page **performante** (LightHouse) et **responsive** j'ai choisi de partir sur des sections simples et animées.

## ⏳ Temps passé sur le test
- **Design** : 4H
- **Développement** : ~ 13H50 (soit environ 2 jours types d'entreprise de 7h)

## La landing page
Elle est disponible à l'URL suivante : https://theempireneedsyou.netlify.app/

---

## 🛠️ Stack technique

### Langages & Framework
- **HTML5**
- **CSS3**
- **TypeScript**
- **Vue.js 3** Pour la création de composants réutilisables comme les cards

### Animations & Effets
- **GSAP** pour des animations dynamiques et fluides; et notament ScrollTrigger pour lancer les animations des éléments lors de leur entrée dans le viewport
- Transitions CSS pour les effets de survol et interactions

---

##  🎨 Design

- **Figma** : Maquettage sur Figma de la page en desktop et mobile

---

## 💻 Outils de développement

- **IDE** : Visual Studio Code
- **Déploiement** : [Netlify](https://www.netlify.com/) via GitHub
- **Versionning** : Git & GitHub
- **Assistance IA** : ChatGPT pour la génération des textes, envoi du formulaire (fonction .trim pour supprimer les espaces), style du formulaire (styles par défaut des navigateurs), création du fichier **shims-vue.d.ts** pour que TypeScript reconnaisse les fichiers vue.js

---

## 📱 Responsive & Compatibilité

- ✔️ Design **mobile-first**
- ✔️ Compatibilité testée sur :
  - iPhone sur Safari, Chrome
  - Desktop sur Chrome, Brave, Edge
- ✔️ Expérience fluide sur tous les formats d’écran

---

## 🧪 Performances (Lighthouse)

- **Performance** ✅
- **Accessibilité** ✅
- **Best Practices** ✅
- **SEO** ✅

Tests réalisés avec **Lighthouse** sur version déployée localement.
avec : 

```bash
npm run build
npx serve dist

---

## 🔧 Lancer le projet localement

```bash
git clone https://github.com/ton-utilisateur/TheEmpireNeedsYou.git
cd TheEmpireNeedsYou
npm install
npm run dev