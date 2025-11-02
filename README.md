# AEROVITA — Buildathon Demo

This repository contains a small React + Vite landing page demo adapted from your provided components. It includes a Tailwind CSS setup and a responsive UI.

What this repo contains:
- Source code in `src/` (components, styles)
- Vite dev server and build commands (`npm run dev`, `npm run build`)
- Tailwind CSS build configured via `postcss.config.cjs` and `tailwind.config.cjs`
- A GitHub Actions workflow to build and deploy to GitHub Pages automatically when you push to the default branch

Quick local setup

1. Install dependencies (cross-platform):

```
npm install
```

2. Start dev server:

```
npm run dev
```

Open the URL shown in the terminal (e.g. http://localhost:5173 or another port Vite chooses).

Production build

```
npm run build
```

The build artifacts will be output to `dist/`.

Firebase setup (optional)

1. Create a Firebase project at https://console.firebase.google.com/ and add a Web app.
2. Copy your Firebase config values and create a file named `.env.local` in the project root with these variables (or set them in your CI):

```
VITE_FIREBASE_API_KEY=...
VITE_FIREBASE_AUTH_DOMAIN=...
VITE_FIREBASE_PROJECT_ID=...
VITE_FIREBASE_STORAGE_BUCKET=...
VITE_FIREBASE_MESSAGING_SENDER_ID=...
VITE_FIREBASE_APP_ID=...
```

3. The code in `src/firebase/init.js` will automatically read these variables and initialize Firestore. The contact form in `src/components/home/Contact.jsx` will save submissions to a `contacts` collection.

Security note: Firebase client config is safe to include in frontend code — it's not a secret. However, protect any server keys and consider adding security rules in the Firebase console to prevent abuse.

Deploy to GitHub (automatic via Actions)

1. Create a new repository on GitHub (use the website or `gh repo create`).
2. Add the remote and push your code (example commands below).
3. When you push to the default branch (usually `main`), the GitHub Actions workflow will run, build the site, and deploy to GitHub Pages.

Commands to push (replace `<GITHUB-URL>` with the repo URL):

```
git init
git add .
git commit -m "Initial commit: AEROVITA demo"
git remote add origin <GITHUB-URL>
git branch -M main
git push -u origin main
```

After the push, open the Actions tab in your GitHub repo to watch the `deploy.yml` workflow. When it completes, your site will be published to GitHub Pages. GitHub may take a minute or two to provision the Pages site.

Notes & troubleshooting

- If the workflow fails, open the run log in Actions to see build errors. Common issues are missing dependencies or syntax errors.
- If you want a custom domain, add a `CNAME` file and configure DNS in GitHub Pages settings.

If you want, I can (a) create the GitHub repository for you if you provide access, or (b) guide you step-by-step while you run the push commands. Tell me which you prefer.