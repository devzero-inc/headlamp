# Devzero headlamp

A fork of headlamp for devzero. Leverages dynamic-clusters plugin to ensure clusters are only available/registerable client side.

## Current setup

Backend:
- rewritten api routes on nextjs/backend
- plugin route hardcoded to return ['dynamic-plugins']

Frontend:
- no modifications on frontend, except PUBLIC_URL env var set to "/headlamp"

## Setup guide
- run `npm run build-dz` 
- copy build folder over to nextjs public folder
- rename to "headlamp"
