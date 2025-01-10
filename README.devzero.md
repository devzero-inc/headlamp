# Devzero headlamp

A fork of headlamp for devzero. Leverages dynamic-clusters plugin to ensure clusters are only available/registerable client side.

## Current setup

Backend:
- rewritten api routes on nextjs/backend
- plugin route hardcoded to return ['dynamic-plugins', 'change-logo'] and any other enabled plugin

Frontend:
- PUBLIC_URL set to "/headlamp"
- plugins built and copied to frontend build folder

## Setup guide

Two short steps to update headlamp on `devzero-website`

### 1. Prepare build files from this repository

**Option A (via script)**

```
npm --prefix ./frontend install
npm --prefix ./frontend run build-dz

npm --prefix ./plugins/devzero/dynamic-clusters install
npm --prefix ./plugins/devzero/dynamic-clusters run build
mkdir -p ./frontend/build/plugins/dynamic-clusters
cp ./plugins/devzero/dynamic-clusters/dist/main.js ./frontend/build/plugins/dynamic-clusters/main.js
cp ./plugins/devzero/dynamic-clusters/package.json ./frontend/build/plugins/dynamic-clusters/package.json

npm --prefix ./plugins/devzero/change-logo install
npm --prefix ./plugins/devzero/change-logo run build
mkdir -p ./frontend/build/plugins/change-logo
cp ./plugins/devzero/change-logo/dist/main.js ./frontend/build/plugins/change-logo/main.js
cp ./plugins/devzero/change-logo/package.json ./frontend/build/plugins/change-logo/package.json
```

**Option B (manualy)**

- install and build /frontend
- install and build each /plugins/devzero/PLUGIN_NAME
- for each plugin copy `/dist/main.js` and `/package.json` to /frontend/build/plugins/PLUGIN_NAME/

### 2. Copy built files to devzero-website repository
- copy contents of `/frontend/build` to `/devzero-website/public/headlamp` 
