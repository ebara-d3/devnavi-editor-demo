# devnavi-editor-demo
This is the repo which will contain demo implementations of various rich-tech text editors.

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

## Add a new page

To add a new page with a new implementation, first
add a route (if you'd like for it to be in a different page)
in `src/router/index.ts` under `routes` property:

```
{
  path: '/editor3',
  name: 'editor3',
  component: Editor3View
}
```

Then add a link to this view in `src/App.vue`:

```vue
  <nav class="nav">
    <ul>
      <li>
      <RouterLink to="/">Editor 1</RouterLink>
      </li>
      <li>
      <RouterLink to="/editor2">Editor 2</RouterLink>
      </li>
+     <li>
+      <RouterLink to="/editor3">Editor 3</RouterLink>
+     </li>
    </ul>
```

Lastly, create a view component under `src/views/`, with your implementation.

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

``
