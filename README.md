# typescript-airbnb-eslint-config-template

This repository provides a starter template for TypeScript projects with a pre-configured setup for ESLint and Prettier following the Airbnb style guide. It includes all necessary configurations and dependencies to ensure consistent code quality and formatting throughout your project.

### Commands

```sh
npm run build

npm run start

npm run dev # Uses nodemon to watch and recompile TypeScript files on each save, then restarts the application using ts-node. Ideal for development with live reloading.

npm run lint # Runs ESLint to check for code errors in all .ts and .tsx files.

npm run lint:fix # Runs ESLint in fix mode to automatically correct fixable issues in all .ts and .tsx files.

npm run format # Uses Prettier to format code in the src directory files: .js, .jsx, .ts, .tsx, .json, .css, .scss, .md.
```

### VS Code

For a better development experience, it's recommended to configure VS Code to format and lint your code on save. This template already includes a local VS Code configuration, but you may want to make it global. If you want to do so, add the following settings to your VS Code settings.json:

#### settings.json

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ]
}
```

### React Projects

If your project uses React, you should remove `base` from both `airbnb-base` and `airbnb-typescript/base` in your `.eslintrc.js` configuration. You should also add `react` to the `plugins` array. The modified configuration will look like this:

```js
module.exports = {
  root: true,
  parser: '@typescript-eslint/parser',
  parserOptions: {
    project: './tsconfig.json',
  },
  plugins: ['@typescript-eslint', 'import', 'prettier', 'react'],
  extends: [
    'airbnb',
    'airbnb-typescript',
    'prettier',
    'plugin:@typescript-eslint/recommended',
    'plugin:import/typescript',
  ],
  rules: {
    'prettier/prettier': 'error',
  },
};
```
