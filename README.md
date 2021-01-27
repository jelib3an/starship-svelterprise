# Starship Svelterprise

Fun with Svelte. Demonstrating concepts such as `reactive declarations`, `props`, `event forwarding`, `component bindings`, `this binding`, `slots`, and `context api`.

## Live demo

Play around on the [REPL](https://svelte.dev/repl/6a86a65834fc47f1a2c929527b30a2d4?version=3.31.2). 

---

## Get started

```bash
npm install
npm run dev
```
---

## Usage

```svelte
<Starfield width="500" height="250">
  <Starship posX="100" posY="150" />
  <Starship shipClass="galaxy" posX="275" posY="50" />
</Starfield>
```
