# Piplosion auf itch.io – Seite einrichten

Alles, was beim Anlegen der Projektseite auf itch.io einzutragen ist.
Erst als **Draft** speichern, Vorschau testen, dann auf **Public** stellen.

## Dateien

| Was | Datei |
|---|---|
| Web-Version (im Browser spielbar) | `piplosion-web-X.Y.Z.zip` – lokal: `piplosion/dist/`, sonst Artefakt des GitHub-Builds |
| Android-APK | aus dem [neuesten Release](https://github.com/cleuenberg/piplosion-android/releases/latest) |
| Titelbild (Cover, 630 × 500) | `assets/itch-cover.png` |
| Screenshots | `assets/itch-screenshots/01-gameplay.png` … `06-hi-scores.png` (1080 × 2160 – itch.io erlaubt max. 2160 px Höhe; `assets/screenshots/` ist der Zapstore-Satz mit 2280 px) |

## Grundeinstellungen („Create new project“)

- **Title:** Piplosion
- **Project URL:** `…itch.io/piplosion`
- **Short description or tagline:**
  `Chain dice, set off bombs and keep the board clear – a retro dice puzzle.`
- **Classification:** Games
- **Kind of project:** HTML
- **Release status:** Released
- **Pricing:** Entscheidung bei Ihnen. Empfehlung: **„$0 or donate“** (kostenlos, freiwillige Spende möglich).
  Alternativ „No payments“.

## Uploads

1. **Web-ZIP** hochladen → Häkchen **„This file will be played in the browser“**.
2. **APK** hochladen → Plattform **Android** anhaken.

## Embed options (Web-Version)

- **Viewport dimensions:** `450` × `800`
- **Frame options:**
  - ✅ **Mobile friendly** → Orientation: **Portrait**
  - ✅ **Fullscreen button**
  - ☐ Automatically start on page load (aus lassen – der Klick auf „Run game“ erlaubt dem Browser auch den Ton)
  - ☐ SharedArrayBuffer support (nicht nötig)

## Details

**Description** (in den Editor einfügen):

> **Piplosion** is a retro dice puzzle in 16-bit style.
>
> Dice keep dropping into a 6 × 12 grid. Tap or swipe to link **2–6 neighbouring dice** – matching pips (4·4·4) or a straight (2·3·4·5) – and clear them before the stack reaches the top.
>
> **Special dice**
> - ★ **Joker** – fits anywhere (as long as real dice outnumber jokers)
> - 💣 **Bomb** – blasts everything around it, neighbouring bombs chain-react
> - ⏱ **Stopwatch** – freezes new rows for 3 seconds
> - 🧲 **Magnet** – pulls every row together and closes the gaps
>
> **More**
> - MIX meter: three bombs charge it, then reshuffle the whole board
> - Tap the preview to drop the next row early for bonus points
> - Board-clear bonus, 6-chain fanfare and rocket rewards at 25k, 50k, 75k and 100k points
> - Chiptune sound effects and menu music
> - English, German and French
> - Local hi-score table and an optional global list
>
> **Play** right here in the browser, or install the Android app (APK below, also on [Zapstore](https://zapstore.dev)).
> Also playable at [piplosion.app](https://piplosion.app) – installable and offline-capable.
>
> *Privacy: the global hi-score list is optional. Only name, score, level, date and game version are stored; server logs are anonymized within 24 hours.*

- **Genre:** Puzzle
- **Tags** (max. 10): `puzzle`, `dice`, `pixel-art`, `retro`, `arcade`, `chiptune`, `16-bit`, `casual`, `singleplayer`, `offline`
- **AI generation disclosure:** itch.io fragt, ob das Projekt KI-erzeugte Inhalte enthält.
  Code, Pixel-Grafiken, Musik, Soundeffekte und Texte sind mit KI-Unterstützung (Claude) entstanden –
  hier also ehrlich **„Yes“** angeben und die betroffenen Bereiche anhaken.
- **Custom noun:** leer lassen
- **Community:** Comments (empfohlen)
- **Visibility:** erst *Draft*, nach dem Test *Public*

## Aussehen der Seite („Edit theme“, passend zum Spiel)

- Background: `#0b0a1e` · Inner background: `#15143a`
- Text: `#f4f0ff` · Link / Button: `#ffe14a`
- Cover: `assets/itch-cover.png`, Screenshots aus `assets/itch-screenshots/` in der Reihenfolge 01 … 06

## Automatische Updates (butler)

Sobald die Seite existiert, lädt GitHub Actions jedes neue Release automatisch hoch
(Web-Version in den Kanal `html5`, APK in den Kanal `android`). Einmalig einrichten:

1. itch.io → **Settings → API keys → Generate new API key**
2. Im Terminal (Schlüssel einfügen, wenn danach gefragt wird):
   ```bash
   gh secret set BUTLER_API_KEY -R cleuenberg/piplosion
   gh variable set ITCH_GAME -R cleuenberg/piplosion --body "IHR-ITCH-NAME/piplosion"
   ```
3. Nach dem ersten automatischen Upload in den Uploads einmal prüfen, dass die Web-Datei
   als „played in the browser“ markiert ist.
