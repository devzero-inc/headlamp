# Devzero headlamp

A fork of headlamp for devzero. Leverages dynamic-clusters plugin to ensure clusters are only available/registerable client side.

## Current setup

Backend:
- rewritten api routes on nextjs/backend
- plugin route hardcoded to return ['dynamic-plugins']

Frontend:
- PUBLIC_URL set to "/headlamp"
- dynamic-clusters plugin enabled

## Setup guide

- install and build frontend
- install and build dynamic-clusters plugin
- copy dynamic-clusters build stuff into frontend build stuff
- copy the frontend/build to nextjs public/headlamp
  
```
npm --prefix ./frontend install
npm --prefix ./frontend run build-dz
npm --prefix ./plugins/examples/dynamic-clusters install
npm --prefix ./plugins/examples/dynamic-clusters run build
mkdir -p ./frontend/build/plugins/dynamic-clusters
cp ./plugins/examples/dynamic-clusters/dist/main.js ./frontend/build/plugins/dynamic-clusters/main.js
cp ./plugins/examples/dynamic-clusters/package.json ./frontend/build/plugins/dynamic-clusters/package.json
```
