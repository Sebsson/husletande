# Husletande 🏡

En enkel, mobilanpassad webbapp med två sidor som stöd när ni letar bostad i Sverige:

1. **Checklista för visning** — viktiga saker att kolla på medan ni går runt på en visning. Bocka av punkterna, lägg till egna, och nollställ inför nästa visning.
2. **Inför köpet** — råd, regler och saker att tänka på vid bostadsköp (ekonomi, förening, budgivning, undersökningsplikt, kontrakt, skatt m.m.).

Allt ligger i en enda fil ([`index.html`](index.html)) — ingen server, inget byggsteg, inga externa beroenden utöver Google Fonts. Det du bockar av i checklistan sparas lokalt i webbläsaren (`localStorage`), så inget skickas någonstans.

## Använda appen

Öppna [`index.html`](index.html) direkt i webbläsaren, eller publicera den på GitHub Pages (se nedan) och öppna den på mobilen under visningen.

Designen är **mobile first** — gjord för att hållas i handen på en visning — men fungerar lika bra på surfplatta och dator.

## Publicera på GitHub Pages

Eftersom appen är en enda statisk fil passar GitHub Pages perfekt:

1. Pusha koden till ett GitHub-repo (filen måste heta `index.html` och ligga i repots rot — det gör den).
2. Gå till **Settings → Pages** i repot.
3. Under **Build and deployment → Source**, välj **Deploy from a branch**.
4. Välj branchen `main` och mappen `/ (root)`, klicka **Save**.
5. Efter en stund nås appen på `https://<ditt-användarnamn>.github.io/<repo-namn>/`.

Spara den adressen som genväg på mobilens hemskärm så öppnas checklistan som en app.

## Utveckling

Förhandsgranska lokalt med valfri statisk server:

```bash
python -m http.server 8765
# öppna http://localhost:8765/
```

All layout och logik finns i [`index.html`](index.html): checklistans punkter ligger i `CHECKLIST`-arrayen och köpguiden i `GUIDE_SECTIONS` — redigera dem direkt i filen för att ändra innehållet.
