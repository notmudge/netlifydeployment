# Quarto + Netlify Data Science Blog (with protected CV)

## Quick start
1. Install Quarto: https://quarto.org/docs/get-started/
2. Render locally:
   ```bash
   quarto render
   quarto preview
   ```
3. Deploy to Netlify (choose one):
   - **Manual:** `quarto publish netlify` (auth via browser)
   - **CI from GitHub:** Connect repo in Netlify; build command `quarto render`, publish dir `_site`

## Protect the `/cv/` page
- **Option A — Basic Auth:** edit `_headers` to set `Basic-Auth: username:password` (requires paid plan per Netlify docs).
- **Option B — Identity + Roles (free):**
  - Enable **Identity** in Netlify dashboard.
  - Invite your email; assign role `cv`.
  - The `netlify.toml` already contains redirects that allow only role `cv` to access `/cv/*` and redirect others to `/login`.

## Writing posts
- Add `.qmd` (or `.ipynb`) under `posts/`. The homepage lists posts automatically.

## Data science
- Code cells run with Python via Jupyter. Replace sample code with your analysis and plots.