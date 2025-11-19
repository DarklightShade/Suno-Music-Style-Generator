# The Sonic Architect (GitHub Pages Demo)

Single-page web app to generate:
- A concise **short tag string** for Suno / Udio.
- A **Sonic Architecture** description with four Markdown sections.

This demo runs fully in the browser:
- Short tags are built locally from your inputs.
- Deep analysis is a static template (no API calls).
- No API keys or backend required.

## Deploy to GitHub Pages

1. Sign in at https://github.com (or create a free account).
2. Click **New** (top-left) to create a repository.
3. Name it e.g. `sonic-architect`.
   - Visibility: **Public**
   - You do not need to tick any extra boxes.
4. Click **Create repository**.

### Upload the app files

1. On the new repo page, click **Add file → Upload files**.
2. Upload:
   - `index.html`
   - `README.md` (this file)
3. Scroll down and click **Commit changes**.

### Enable GitHub Pages

1. Go to the repo **Settings**.
2. In the side menu, click **Pages**.
3. Under **Source**:
   - Choose **Deploy from a branch**.
   - Branch: `main`
   - Folder: `/ (root)`.
4. Click **Save**.

GitHub will build the site and show you a URL such as:

> https://YOUR-USERNAME.github.io/sonic-architect

Open that URL to use The Sonic Architect from anywhere.

## Later: connect a real AI backend

If you want real AI-generated analysis:

- Build a small backend (serverless function or simple server) that:
  - Accepts POST JSON with the four inputs.
  - Calls your LLM with the System Instruction you defined.
  - Returns JSON: `{ "short_tags": "...", "deep_analysis": "..." }`.

Then change in `index.html`:

```js
const USE_DEMO_MODE = false;
const BACKEND_URL = "https://your-real-backend.example.com/sonic-architect";
```

The front-end will then use live LLM output.
