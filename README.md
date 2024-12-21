# Next.js 15 App Dir: Silent Data Loss Bug

This repository demonstrates a subtle bug in Next.js 15's `app` directory. When using the built-in `fetch` within a component's `useEffect` hook, coupled with rapid client-side navigation, data loss can occur without any visible errors.  This happens because the component unmounts before a previous fetch completes, rendering the response useless.  The solution involves careful promise management using `AbortController`.

## Reproducing the Bug

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate between the routes. Observe that data fetching might fail silently.