# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

-  [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
-  [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

-  Configure the top-level `parserOptions` property like this:

````js
export default tseslint.config({
  # Electronic Health Record System

  This repository contains a React + TypeScript single-page application built with Vite. It is the graduation project EHR dashboard used to manage staff, patients and bookings, with role-based access, internationalization, and modern developer tools.

  **Key features**

  - Role-based protected routes (`admin`, `doctor`, `receptionist`, etc.)
  - Data fetching & caching with `@tanstack/react-query` and DevTools
  - Internationalization (`en`, `ar`) via `react-i18next`
  - Forms and validation with `formik` and `yup`
  - Tailwind CSS + Radix UI primitives for consistent UI
  - Charts (`recharts`), virtualization (`react-window`), enhanced selects (`react-select`)
  - Toast notifications with `react-toastify`

  **Tech stack**

  - Vite
  - React 18 + TypeScript
  - Tailwind CSS
  - @tanstack/react-query
  - react-router-dom v6
  - react-i18next

  ## Quick start

  Requirements:

  - Node.js (16+ recommended)
  - npm, yarn, or pnpm

  Install dependencies:

  ```bash
  npm install
````

Run dev server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Preview production build locally:

```bash
npm run preview
```

## Environment variables

Provide backend URL via Vite env var:

```bash
VITE_API_URL=https://api.example.com/
```

This is used by the API client in [src/services/apiCall.ts](src/services/apiCall.ts).

## Useful scripts

-  `dev`: start the Vite dev server
-  `build`: run `tsc -b` then `vite build`
-  `preview`: preview the production bundle
-  `start`: `vite preview --port 3091`
-  `lint`: run ESLint
-  `format`: run Prettier

## Where to look in the codebase

-  Entrypoint: [src/main.tsx](src/main.tsx)
-  Routing and app providers: [src/App.tsx](src/App.tsx)
-  API client: [src/services/apiCall.ts](src/services/apiCall.ts)
-  Auth endpoints: [src/services/apiAuth.ts](src/services/apiAuth.ts)
-  Translations and i18n: [src/i18n.ts](src/i18n.ts) and `src/translations`
-  Constants and query keys: [src/constants.ts](src/constants.ts)

### Routing & permissions

Routes are declared in [src/App.tsx](src/App.tsx). Pages are composed using layout components and protected by `ProtectedRoute` which checks `allowedRoles`. Example routes implemented:

-  `/dashboard` — admin
-  `/staff-management/doctors`, `/staff-management/nurses`, `/staff-management/clinics`, `/staff-management/specializations` — various role restrictions
-  `/patients` and `/patients/:patientId` — admin & doctor
-  `/bookings`, `/add-booking` — admin & receptionist

### API & auth

The `apiCall` helper attaches `Authorization` and `accept-language` headers and parses responses. Authentication endpoints like `login`, `logout` and `me` are in [src/services/apiAuth.ts](src/services/apiAuth.ts).

### Internationalization

Supported languages are defined in [src/constants.ts](src/constants.ts) and wired in [src/i18n.ts](src/i18n.ts). Translation JSONs are under `src/translations/en` and `src/translations/ar`.

## Development tips

-  Use React Query DevTools (enabled in `App.tsx`) to inspect cache and active queries.
-  Keep `VITE_API_URL` set during development to avoid runtime errors.
-  Run `npm run lint` and `npm run format` before committing changes.

## Deployment

The app builds into static files and can be hosted on Vercel, Netlify, or any static hosting provider. Ensure `VITE_API_URL` points to the production API.

## Contributing

Contributions are welcome. Follow the project's styling and lint rules, add translations for new UI strings, and ensure any API changes are reflected in the client services.

---

If you want, I can next:

-  add a short developer guide for creating bookings and patients,
-  generate a runnable Postman collection or API contract summary, or
-  create a small architecture diagram and folder map.

Which of these would you like me to do next?
