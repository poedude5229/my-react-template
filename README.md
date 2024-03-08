# React Vite Template

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

Here's a good pack for icons: 

- [React Icons](https://react-icons.github.io/react-icons/)

When setting up a React app with Vite, you can run this to generate a template:
```
npm create vite@4.4.1 my-react-vite-template -- --template react
```
Follow the commands it gives you in the terminal.
```
npm install -D vite-plugin-eslint
```
The above command gives you a helpful linter package. In __vite.config.js__ The ESlint plugin should be added to the  list of imports. 

Then, in `defineConfig`, add `eslint` to the plugins array:
```
export default defineConfig(({ mode }) => ({ // <-- Change this line too!
  plugins: [
    react(),
    eslint({
      lintOnStart: true,
      failOnError: mode === "production"
    })
  ],
  server: {
    open: true
  }
}))
```
Next in __.eslintrc.cjs__ add this under rules:
```
rules: {
    'react-refresh/only-export-components': [
      'warn',
      { allowConstantExport: true },
    ],
    'react/prop-types': 'off' // <-- Add this line
  },
```
Add `'node_modules'` in ignorePatterns array in this same file. 

Take out all of React/Vite's needless self promotion by removing the first div in __src/App.jsx__, 
deleting the __assets__ folder entirely,
removing the __public/vite.svg__,
deleting __App.css__ and removing its import in __App.jsx__
and deleting the content of __index.css__ to add your own later. 

Put this all in a git repo and thank me later!
