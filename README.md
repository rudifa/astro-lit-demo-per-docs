# Astro + Lit Demo

This project demonstrates how to integrate Lit components with Astro, based on the Astro Starter Kit: Minimal template.

## 🚀 Project Structure

```text
/
├── public/
├── src/
│   ├── components/
│   │   └── MyComponent.js
│   └── pages/
│       └── index.astro
├── astro.config.mjs
└── package.json
```

- `src/pages/`: Contains Astro pages
- `src/components/`: Houses Lit components
- `public/`: Stores static assets

## 🧞 Commands

| Command             | Action                                           |
| :------------------ | :----------------------------------------------- |
| `npm install`       | Installs dependencies                            |
| `npm run dev`       | Starts local dev server at `localhost:4321`      |
| `npm run build`     | Build your production site to `./dist/`          |
| `npm run preview`   | Preview your build locally, before deploying     |
| `npm run astro ...` | Run CLI commands like `astro add`, `astro check` |

## 🚀 Getting Started

1. Clone this repository
2. Run `npm install`
3. Start the dev server with `npm run dev`

## 📚 Adding Lit Components to Astro

1. Install the @astrojs/lit integration:

   ```sh
   npm install @astrojs/lit lit
   ```

2. Configure Astro to use Lit in `astro.config.mjs`:

   ```javascript
   import {defineConfig} from "astro/config";
   import lit from "@astrojs/lit";

   export default defineConfig({
     integrations: [lit()],
   });
   ```

3. Create a Lit component in `src/components/`:

   ```javascript
   import {LitElement, html} from "lit";

   export class MyComponent extends LitElement {
     render() {
       return html`<p>Hello from Lit!</p>`;
     }
   }

   customElements.define("my-component", MyComponent);
   ```

4. Use the Lit component in an Astro page:

   ```astro
   ---
   import { MyComponent } from '../components/MyComponent';
   ---

   <MyComponent client:load />
   ```

## 🔑 Key Integration Points

1. **Imports**: Correctly import from Lit and use proper paths in Astro files.
2. **Component Definition**: Extend `LitElement` and use `customElements.define()`.
3. **Astro Usage**: Use PascalCase for component names and apply client directives.
4. **Shadow DOM**: Lit components use Shadow DOM by default.
5. **Reactivity**: Use `static properties` for reactive properties in Lit components.
6. **Styling**: Define styles using `static styles` for component-scoped CSS.

## 👀 Learn More

- [Astro Documentation](https://docs.astro.build)
- [Lit Documentation](https://lit.dev/)
- [@astrojs/lit Integration Guide](https://docs.astro.build/en/guides/integrations-guide/lit/)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📝 License

This project is [MIT](LICENSE) licensed.
