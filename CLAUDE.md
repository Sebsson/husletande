# CLAUDE.md

Vägledning för Claude Code när du arbetar i det här repot.

## ⚠️ ALLTID FÖRST: hämta senaste ändringarna

Innan du börjar arbeta — och innan du läser/redigerar filer — kör alltid:

```bash
git fetch origin
git status -sb          # ser om branchen ligger efter origin/main
git log --oneline HEAD..origin/main   # vad har hänt på main?
```

Om branchen ligger efter `origin/main`, uppdatera den (t.ex. `git merge --ff-only origin/main` eller `git pull --rebase`) **innan** du ändrar något.

**Varför:** worktrees kan skapas från en gammal main. Den här appen har redan byggts om en gång (hela `husletande.html` togs bort och flyttades till `index.html`). Redigerar du utan att först hämta riskerar du att jobba på en föråldrad eller raderad fil — allt arbete blir då bortkastat.

## Projektet

- **Husletande** — en liten, statisk app som hjälper till vid bostadssök/visningar. Ren HTML/CSS/JS, ingen byggkedja.
- Hela appen ligger i **`index.html`** (en enda fil med inline `<style>` och `<script>`). `index.html` är roten.
- Tvåsides-app: **Checklista** (saker att kolla på en visning) och **Inför köpet** (guide).
- State sparas i `localStorage` under nyckeln `husletande_visning_v1`.
- **Kontext:** sökandet gäller **hus med äganderätt**, inte bostadsrätter/lägenheter. Anpassa checkpunkter och guidetext därefter (inte förening/månadsavgift/hiss osv.).

## Design: mobile first

Appen används främst **i mobilen på plats under visningar** — utgå alltid från mobil först.

- Designa och testa för smal skärm först (~360–390 px breda), bredda sedan uppåt med `@media(min-width:720px)`-brytpunkter — inte tvärtom.
- Tryckytor ska vara fingervänliga (minst ~40 px höga/breda); undvik beroende av hover.
- Verifiera alltid layouten i mobilstorlek innan du anser dig klar (`preview_resize` till t.ex. 390 px).
- Respektera `env(safe-area-inset-*)` (notch/hemknapp) — finns redan i header och bottennavigering.

## Köra / förhandsvisa

Statisk fil — servera katalogen och öppna `index.html`:

```bash
python -m http.server 8765   # öppna sedan http://localhost:8765/
```
