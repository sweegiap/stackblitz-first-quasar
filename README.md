# Quasar App (app-vite)

My First Quasar Project on Stackblitz

Steps:

1. Created using Quasar starter from StackBlitz
2. Following along the Quasar Video Tutorial:
   - https://www.youtube.com/watch?v=GV-D85D9KJQ
3. Switch from StackBlitz to DevPod Devcontainer
   - StackBlitz push to GitHub issues with email protection
4. Switch to Local Development + Quasar BEX of Todo
   - Follows tutorial: https://www.thisdot.co/blog/how-to-create-browser-extensions-using-quasar-and-vue-3
   - Add Bex mode to local checkout, plus some fixes to package.json, and `<keep-alive/>`
   - Issues to fix:
     - [ ] Need persistance for todo
     - [ ] Popup size too small
     - [ ] Proper layouts in Pages (Options, Popup, NewTab(?))

## Install the dependencies

```bash
yarn
# or
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)

```bash
quasar dev
```

### Lint the files

```bash
yarn lint
# or
npm run lint
```

### Format the files

```bash
yarn format
# or
npm run format
```

### Build the app for production

```bash
quasar build
```

### Customize the configuration

See [Configuring quasar.config.js](https://v2.quasar.dev/quasar-cli-vite/quasar-config-js).
