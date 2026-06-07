# Husletande 🏡

En privat husletarapp för ett par som söker bostad i Sverige. Allt samlat på ett ställe — objekt, betyg, jämförelser, budlogg och beslutsstöd — utan koppling till Hemnet eller externa tjänster. All data sparas lokalt i webbläsaren (`localStorage`).

## Använda appen

Öppna [`husletande.html`](husletande.html) direkt i webbläsaren. Inga byggsteg, ingen server krävs.

## Funktioner

- **Objektlista** med snabböversikt (adress, pris, storlek, betyg, status) samt filter och sortering.
- **Snabb-tillägg** för att fånga ett objekt på sekunder, och **"Klistra in & tolka"** som läser ut fält ur en inklistrad annonstext (Hemnet/Booli) — helt lokalt.
- **Detaljvy** med all fakta: pris (utgångs-/slutpris), kvm, rum, våning, byggår, avgift, drift, bostadsrättsförening, mäklare och visning.
- **Betygsättning** per partner i fem kategorier (läge, skick, planlösning, pris/värde, potential) med aggregerat gemensamt betyg.
- **Jämförelsevy** sida vid sida för 2–4 objekt.
- **Kommentarer** per objekt med avsändare och tidsstämpel.
- **Checklista** inför visning, förifylld och kompletterbar.
- **Budlogg** med budrundor, tidpunkt och motbud.
- **Decision board** med de tre högst betygsatta aktiva objekten.
- **Inför köpet** — råd, regler och saker att tänka på vid bostadsköp i Sverige.

## Dela mellan enheter

Appens data ligger i webbläsarens `localStorage` på varje enhet — den följer alltså **inte** automatiskt med när du klonar repot på en annan dator. För att flytta över era objekt:

1. **Inställningar → Exportera all data (JSON)** på den enhet som har datan.
2. Flytta filen till den andra enheten (mejl, molnlagring etc.).
3. **Inställningar → Importera data (JSON)** och välj *Slå ihop* (synkar) eller *Ersätt allt*.

Repot innehåller alltså själva appen; den personliga datan flyttar du via export/import.

## Utveckling

Förhandsgranskning via en enkel statisk server:

```bash
python -m http.server 8765
# öppna http://localhost:8765/husletande.html
```
