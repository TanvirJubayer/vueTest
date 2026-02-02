# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about IDE Support for Vue in the [Vue Docs Scaling up Guide](https://vuejs.org/guide/scaling-up/tooling.html#ide-support).


php artisan make:controller api/CustomerController --api

---

## Mock API (json-server) 💡

A quick mock API using `json-server` is included. Run it in a separate terminal:

```bash
npm run api
```

The API will be available at `http://localhost:3000/customers` and the app calls `/api/customers` (Vite proxies `/api` → the json-server port).

