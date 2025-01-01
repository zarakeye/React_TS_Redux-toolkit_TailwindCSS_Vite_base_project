# React + TypeScript + Vite + ESLint + Redux-Toolkit + TailwindCSS

This template provides a basic React + TypeScript + Vite + ESLint + Redux-Toolkit + TailwindCSS setup.

## Getting started

First, run `npm create vite@latest my-app` to create a new project and choose React  and TypeScript + SW.

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```

Setup React with Vite and Tailwind CSS

Pour initialiser un projet Vite.js avec React, TypeScript, Redux Toolkit, et Tailwind CSS, suivez ces étapes :

1. **Créer le projet** :
   - Assurez-vous d'avoir Node.js et npm installés sur votre système.
   - Ouvrez votre terminal et naviguez vers le dossier où vous souhaitez créer votre projet.
   - Exécutez la commande suivante pour créer un nouveau projet Vite avec React et TypeScript :
     ```
     npm create vite@latest my-app -- --template react-ts
     ```
   - Remplacez `my-app` par le nom de votre projet.

2. **Installer les dépendances nécessaires** :
   - Naviguez dans le dossier de votre projet nouvellement créé.
   - Exécutez la commande suivante pour installer les dépendances :
     ```
     npm install --save-dev tailwindcss postcss autoprefixer
     npx tailwindcss init -p
     ```

3. **Configurer Tailwind CSS** :
   - Ajoutez les chemins de vos fichiers de modèle dans votre fichier `tailwind.config.js` :
     ```javascript
     /** @type {import('tailwindcss').Config} */
     module.exports = {
       content: [
         "./index.html",
         "./src/**/*.{js,ts,jsx,tsx}",
       ],
       theme: {
         extend: {},
       },
       plugins: [],
     }
     ```
   - Ajoutez les directives Tailwind dans votre fichier CSS, généralement `src/index.css` :
     ```css
     @tailwind base;
     @tailwind components;
     @tailwind utilities;
     ```

4. **Configurer Redux Toolkit** :
   - Installez Redux Toolkit en utilisant la commande suivante :
     ```
     npm install @reduxjs/toolkit react-redux
     ```
   - Créez un dossier `store` dans le dossier `src`.
   - Dans le dossier `store`, créez deux fichiers : `slice.ts` et `store.ts`.
   - Configurez votre store et ses slices dans ces fichiers.

5. **Lancer le serveur de développement** :
   - Exécutez la commande suivante pour démarrer le serveur de développement :
     ```
     npm run dev
     ```
   - Votre application sera disponible à l'adresse `http://localhost:5173`.

En suivant ces étapes, vous pourrez initialiser un projet Vite.js avec React, TypeScript, Redux Toolkit, et Tailwind CSS prêt à être développé.
