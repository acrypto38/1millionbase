# React + TypeScript + Vite

Ce modèle fournit une configuration minimale pour faire fonctionner **React** avec **Vite**, incluant le **rechargement à chaud (HMR)** et quelques règles **ESLint** de base.

## Plugins officiels disponibles

Deux plugins officiels sont actuellement proposés :

- [`@vitejs/plugin-react`](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) — utilise [Babel](https://babeljs.io/) pour le *Fast Refresh*  
- [`@vitejs/plugin-react-swc`](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) — utilise [SWC](https://swc.rs/) pour le *Fast Refresh*

---

## Étendre la configuration ESLint

Si vous développez une application destinée à la production, il est recommandé de mettre à jour la configuration afin d’activer les règles ESLint **sensibles aux types (type-aware)** :

```js
// eslint.config.js
export default tseslint.config({
  extends: [
    // Supprimez ...tseslint.configs.recommended et remplacez-le par ceci :
    ...tseslint.configs.recommendedTypeChecked,
    // Vous pouvez aussi utiliser ceci pour des règles plus strictes :
    ...tseslint.configs.strictTypeChecked,
    // Optionnellement, ajoutez ceci pour les règles de style :
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // autres options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
