# Ionic & Vite & Vue 3

## How Did I Start Up?

### 1. Create a vite project using Vue 3 and TypeScript.

> <https://vitejs.dev/guide/#scaffolding-your-first-vite-project>

```bash
npm init vite@latest
```

### 2. Install vue-router@4

> <https://next.router.vuejs.org/zh/installation.html#npm>

```
npm install vue-router@4
```

### 3. Install Ionic

> <https://ionicframework.com/docs/intro/cdn#ionic--vue>

#### A. Install from npm

To add Ionic Framework to an existing Vue project, install the `@ionic/vue` and `@ionic/vue-router` packages.

```shell
$ npm install @ionic/vue @ionic/vue-router
```

After that, you will need to install the `IonicVue` plugin in your Vue app.

**main.js**

```javascript
import { IonicVue } from '@ionic/vue'

import App from './App.vue'
import router from './router'

const app = createApp(App).use(IonicVue).use(router)

router.isReady().then(() => {
  app.mount('#app')
})
```

Be sure to mount your app once `router.isReady()` has resolved.

#### B. Routing

When setting up routing in your Vue app, you will need to import your dependencies from `@ionic/vue-router` instead of `vue-router`.

**router/index.js**

```javascript
import { createRouter, createWebHistory } from '@ionic/vue-router'

const routes = [
  // routes go here
]

const router = createRouter({
  history: createWebHistory(process.env.BASE_URL),
  routes,
})

export default router
```

#### C. CSS

To include the necessary CSS in a Vue project, add the following to your `main.js` file.

```javascript
/* Core CSS required for Ionic components to work properly */
import '@ionic/vue/css/core.css'

/* Basic CSS for apps built with Ionic */
import '@ionic/vue/css/normalize.css'
import '@ionic/vue/css/structure.css'
import '@ionic/vue/css/typography.css'

/* Optional CSS utils that can be commented out */
import '@ionic/vue/css/padding.css'
import '@ionic/vue/css/float-elements.css'
import '@ionic/vue/css/text-alignment.css'
import '@ionic/vue/css/text-transformation.css'
import '@ionic/vue/css/flex-utils.css'
import '@ionic/vue/css/display.css'
```

From here, you can learn about how to develop with Ionic Framework in our [Ionic Vue Quickstart Guide](https://ionicframework.com/docs/vue/quickstart).

## Configuration

```bash
npm install @types/node -D
```

**tsconfig.json**

```json
{
  "compilerOptions": {
    "target": "esnext",
    "useDefineForClassFields": true,
    "module": "esnext",
    "moduleResolution": "node",
    "strict": true,
    "jsx": "preserve",
    "sourceMap": true,
    "resolveJsonModule": true,
    "esModuleInterop": true,
    "lib": ["esnext", "dom"],
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "include": ["src/**/*.ts", "src/**/*.d.ts", "src/**/*.tsx", "src/**/*.vue"]
}
```

**vite.config.ts**

```typescript
import path from 'path'
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src'),
    },
  },
  plugins: [vue()],
})
```

## Install Capacitor

> <https://capacitorjs.com/docs/getting-started#adding-capacitor-to-your-app>

```bash
npm install @capacitor/core
npm install @capacitor/cli --save-dev
```

## Install Prettier

```bash
npm install --save-dev --save-exact prettier
```

**.prettierrc.json**

```json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": false,
  "singleQuote": true,
  "arrowParens": "avoid",
  "printWidth": 100
}
```
