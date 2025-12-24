
# Hi, I'm Wahb 👋

![Header GIF](./assets/profile-gif.gif)

> Full-Stack developer building fast, reliable web apps that scale — portfolio: https://wahb.space

---

<!-- Badges -->

[![Vercel](https://img.shields.io/badge/Vercel-000000?logo=vercel&logoColor=white&style=for-the-badge)](https://vercel.com)

[![GitHub stats](https://github-readme-stats.vercel.app/api?username=wahb-amir&show_icons=true&theme=radical)](https://github.com/wahb-amir)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=wahb-amir&layout=compact)](https://github.com/wahb-amir)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=wahb-amir&theme=dark)

[![trophy](https://github-profile-trophy.vercel.app/?username=wahb-amir&theme=onedark)](https://github.com/wahb-amir)

![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=wahb-amir.wahb-amir)

---

## About

I build full-stack applications (Next.js, React, Node.js) and small ML/vision experiments that run on everyday hardware. I run and deploy projects on my own Linux VPS and use CI/CD automation to ship fast.

**Quick facts (pulled from wahb.space):**

- Tech stack (front-end): HTML, CSS, Tailwind, JavaScript, TypeScript, React, Next.js, Framer Motion.
- Backend: Node.js, Express, Python, Pandas, PyTorch, MongoDB, MySQL.
- DevOps/Deploy: Docker, Nginx, GitHub Actions.
- Notable projects: Client & Developer Collaboration Platform (live demo: https://dashboard.wahb.space), Modern Online Store (demo link on site), multiple deployed apps and a client portal.

---

## Featured Projects

### Client & Developer Collaboration Platform
- Role: Full-Stack Engineer
- Tech: Next.js, React, Node.js, Tailwind, MongoDB
- Live demo: https://dashboard.wahb.space
- Code: https://github.com/wahb-amir/dev-dashboard and https://github.com/wahb-amir/dashboard

### Modern Online Store
- Role: Full-Stack Developer
- Tech: Next.js, Stripe, Tailwind, MongoDB
- Live demo example: boltform.buttnetworks.com
- Notes: SSR + image optimization for LCP improvements

(See more projects on https://wahb.space)

---

## How to use this README (what I added)

1. **Dynamic GitHub stats** — the cards use `github-readme-stats` endpoints to show live commits, stars, and top languages. If you want to self-host the endpoints (to include private-repo stats or avoid rate limits), deploy your own instance. Example:

```md
[![GitHub stats](https://github-readme-stats.vercel.app/api?username=wahb-amir&show_icons=true&theme=radical)](https://github.com/wahb-amir)
```

2. **Vercel deployment badge** — Vercel doesn't ship a first-class status badge, but you can use a small serverless shim that queries Vercel and renders a badge. Example (uses `vercel-badge`):

```md
![Vercel Status](https://vercelbadge.vercel.app/api/<owner>/<repo>)
```

If you host your own vercel-badge instance you avoid rate limits and keep credentials private.

3. **Animated GIF demo of your portfolio (hero)** — include an animated GIF showing wahb.space in action. Instead of recording by hand, use a GitHub Action that captures the site and commits the GIF to your profile repo (so it renders on GitHub). Example workflow below.

4. **Visitor counter & Trust badges** — visitor badges (e.g., `visitor-badge.laobi.icu`) show profile hits. These services vary in reliability; for a robust solution consider self-hosting a small API that updates a Shields.io badge.

---

## GitHub Action: auto-generate GIF from your site

Create `.github/workflows/generate-gif.yml` in your profile repo (or a utilities repo) to capture `https://wahb.space` and save a GIF to `./assets/profile-gif.gif` and commit it back.

```yaml
name: Generate profile GIF
on:
  schedule:
    - cron: '0 6 * * 0' # weekly (UTC), adjust as you like
  workflow_dispatch: {}

jobs:
  generate-gif:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Generate GIF from website
        uses: PabloLec/website-to-gif@v2
        with:
          url: "https://wahb.space"
          save_path: "/assets/"
          file_name: "profile-gif"
          file_format: "gif"
          final_width: 1024
          final_height: 360
          scroll_step: 25
          time_per_frame: 100
      - name: Commit generated GIF
        run: |
          git config --global user.name "github-actions[bot]"
          git config --global user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add assets/profile-gif.gif
          git commit -m "chore: update profile GIF" || echo "No changes to commit"
          git push
```

This action (PabloLec/website-to-gif) captures your live site and creates a smooth GIF. Put the GIF path in the README (`./assets/profile-gif.gif`) and GitHub will render it.

---

## Vercel status + deploy badge (quick guide)

1. Use the `vercel-badge` public endpoint:

```md
![Vercel](https://vercelbadge.vercel.app/api/wahb-amir/dev-dashboard)
```

Replace `wahb-amir` and `dev-dashboard` with the owner and repo of the project deployed on Vercel. To avoid rate limits, deploy your own `vercel-badge` instance and configure a GitHub OAuth app (see project docs).

2. Alternatively, create your own serverless endpoint that queries Vercel's Deployments API and renders a Shields.io badge. That gives you full control and privacy.

---

## Extra polish ideas (animations & micro-interactions)

- **Animated SVGs** (svg-term or asciinema) to show a terminal demo — embeds nicely and keeps size low.
- **Animated headers**: generate a header image (PNG/WebP/GIF) and host it in the repo; many generators exist.
- **Small JS micro-interactions** for your portfolio (you already use Framer Motion) — keep the README itself static but link to live demos.
- **Profile README Actions**: use GitHub Actions to update snippets (latest blog posts, recent activity) automatically.

---

## Files I added in this repo

- `README.md` (this file)
- `/assets/profile-gif.gif` (auto-generated by GH Action)
- `.github/workflows/generate-gif.yml` (action to produce the GIF)

---

## License

This README template is MIT — adapt freely.

---

*Last updated automatically.*
