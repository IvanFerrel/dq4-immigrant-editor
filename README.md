# Dragon Quest IV DS – Immigrant Town Save Editor

An offline, single-file save editor for the **immigrants (pioneers)** of the Immigrant Town in *Dragon Quest IV: Chapters of the Chosen* (Nintendo DS).

**[Español más abajo](#español)**

## Features
- Edit all **24 received immigrants** (3 pages of 8) and **your own immigrant** (the one you send).
- Type (all 51 types, including the hidden type 50), with sprites **read from your own ROM** (no game graphics are included in this tool), name, gender, age, hobby, sender, hometown and 3-line message (15 characters per line, padded like the game does).
- **Unique IDs** generated automatically, so the game never replaces an immigrant.
- **Templates**: fill all 24 slots with one click.
- **Share codes**: copy an immigrant as text (`DQ4I1:...`) and paste it into someone else's save.
- Blocks out-of-range values that freeze the game (type > 50, gender > 2, age > 7, hobby > 63).
- Recalculates the save checksum.
- Works offline in any browser (PC or Android). No install.

## Usage
1. Download `index.html` and open it in your browser.
2. Load your save (`.sav` / `.dsv` / `.srm`).
   Optional: click **Sprites: abrir tu ROM** and pick your DQ4 DS ROM to show the character sprites (read from `data/G2D/ICON/sure32.mpt`, remembered in your browser).
3. Edit, then click **Guardar** and replace your save file. **Back up your save first.**

Tested with the USA (En,Fr,Es) version. The UI is in Spanish.

## Save format
See [FORMAT.md](FORMAT.md).

---

## Español

Editor offline (un solo archivo HTML) de los **inmigrantes** del pueblo de Dragon Quest IV DS.

- Edita los 24 inmigrantes recibidos y tu inmigrante propio. Los sprites se sacan de **tu propia ROM** (opcional); el editor no incluye gráficos del juego.
- IDs únicos automáticos, plantillas, códigos para compartir y corrección del checksum.
- Bloquea valores que traban el juego.

**Uso:** descarga `index.html`, ábrelo, carga tu partida, edita y guarda. Haz copia de tu partida antes.

## Credits
Research (RAM notes, saves, testing): **Ivan Ferrel**.
