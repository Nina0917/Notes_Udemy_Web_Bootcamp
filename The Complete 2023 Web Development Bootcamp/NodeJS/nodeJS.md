## Node Package Manager

```
npm init
```

- create package.json file

<br>

CJS or ESM

- CJS stands for common JavaScript. It ues "require" to input external package.
- ESM uses "inport" to input package.

<br>

How to let project use ESM?

- Add the following to package.json

```
"type:" "module"
```

<br>

---

## Node and NVM

nvm manages versions of nodejs

```
nvm current
```

- show the current active version of nodejs

```
nvm list
```

- List the available Node.js versions managed by nvm

<br>

Previous conflicts I encountered while installing nvm

- You should uninstall Node.js you previously installed globally or it will results in conflicts.
