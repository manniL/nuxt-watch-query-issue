# Nuxt watch query trailing slash issue

> Demo repo for reproducing the watch query trailing slash issue

When using `watchQuery`, the watchers are **not triggered**, when internally redirecting
to an URL *with trailing slash* and *without the query tring parameter set* (eg to `/query/`)


## Steps to repro:

1. Clone repo
2. Install nuxt-edge (`npm i`)
3. Run dev mode (`npm run dev`)
4. Click on the links and push "forward"/"backward". Look at the URL and the received data.
