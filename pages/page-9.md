# Month 2 Week 3

<style>
  h1 {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>


---

### 🚀 JavaScript Project with Vite – Summary

  * `Named Export`: 
  ```js 
  export const namedFunction = () => {}` → `import { fn }
  ```
  * `Default Export`: 
  ```js
  export default defaultFunction` → `import fn
  ```
  * `Namespace Import`: 
  ```js
  import * as name from "./file"
  ```
  * `Dynamic Import`: 
  ```js
  import("./file").then(...)
  ```


---

## Bundlers

Bundlers are tools that help us convert modules with dependencies into static assets (HTML, CSS, and JS).

> - Bundlers help because browser capabilities are limited.  
> - Examples of bundlers include:  
>   - **Browserify**  
>   - **Grunt** 
>   - **Parcel** 
>   - **Vite** - For this course we will be focusing on Vite
>   - **Webpack** – This was the first major innovation in the bundler space.  
>   - One major challenge with Webpack is that it's complex — however, it's also very flexible.

---

![Image showing how a bundler works](/webpack.png)

<style>
  img {
   object-fit: cover;
   width: 100%;
   height: 100%;
  }
</style>


---

## Lazy Loading

Lazy loading is a feature supported by Webpack that delays loading of modules until they're needed. It helps improve performance by reducing the initial load size. Lazy-loaded modules are also cached by default.

> - Lazy loading is different from conditional rendering.  
> - It works best when focusing on specific routes or pages.  
> - It also enables **dynamic import**, where modules are loaded like functions.

---

## How to Use Vite
> 1. Create your folder using using mkdir "folder name"
> 2. Create a package.json
> - npm init -y
> 3. Install vite as a dev dependency
> - npm i --save -dev vite
> 4. Create the files
> - touch index.[html,css,js]
> 5. Setup gitignore
Setup *Build Script*
> - inside the html file do 
> - html: 5 this will create a boilerplate
> 7. Test: To start using vite set up **dev script**

---

```
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}
```

> 8. Then in the terminal run
> - then **npm run dev** and click on the link of the local host
** When using vite you no longer need **live server**
To host on services like netlify
> - **do npm run build**
> Then **vite preview** - This is the example of what the code will loke like in production
**pnpm uses add while npm uses install**

---

## Option 2  To  install **Vite**
> 1. npm create vite@latest *name of app*
> Then select framework
> 2. Select Vanilla framework and variant Javascript
> 3. *cd* into project
> 4. npm install
> 5. npm run dev
