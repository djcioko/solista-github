# SOLISTA • Live Player

Player audio pentru soliști și evenimente live. Patru programe (seturi), upload direct de fișiere, waveform real, crossfade, normalizare, recomandări după BPM / tonalitate și o roată de spin pentru următoarea piesă.

Aplicația rulează **100% în browser**. Piesele nu se urcă pe un server: metadatele stau în `localStorage`, iar fișierele audio în `IndexedDB`.

## Ce face

- 4 programe: PROGRAM 1–4 (roșu, galben, albastru, verde)
- Upload de fișiere sau foldere, inclusiv drag & drop pe fereastră
- Drag & drop între programe și reordonare în același program
- Play / pause, mod **MANUAL** sau **AUTO** (următoarea piesă doar din același program)
- Crossfade reglabil și normalizare de volum (compresor)
- Waveform din peak-urile reale ale fișierului
- Recomandări armonice (Camelot: exact, relativ, energy boost, subdominant)
- Roată de spin umplută automat din recomandări, cu piese adăugate manual
- Persistare locală: la refresh, lista și audio-ul revin

## Stack

- React 19 + TypeScript
- Vite
- Tailwind CSS 4
- Web Audio API
- IndexedDB

## Pornire locală

Necesită Node.js 20+.

```bash
npm install
npm run dev
```

Deschide [http://localhost:3000](http://localhost:3000).

Build de producție:

```bash
npm run build
npm run preview
```

Verificare TypeScript:

```bash
npm run lint
```

## Structură

```
src/
  App.tsx                 interfață și logică de playlist
  audio/engine.ts         Web Audio: play, crossfade, normalizare
  audio/harmonic.ts       Camelot și scor de recomandare
  components/             waveform și roata de spin
  storage/db.ts           IndexedDB pentru blob-urile audio
  data/defaultRepertoire.ts  cele 4 programe (listele pornesc goale)
public/styles.css
```

## GitHub

Acest zip e pregătit pentru un repo nou:

1. Creează un repository gol pe GitHub (fără README generat, ca să nu intre în conflict).
2. Dezarhivează acest folder.
3. Din folder:

```bash
git init
git add .
git commit -m "Initial commit: SOLISTA Live Player"
git branch -M main
git remote add origin https://github.com/USER/solista-live-player.git
git push -u origin main
```

Nu comite `node_modules/`, `dist/` sau `.env` — sunt deja în `.gitignore`. Fișierele audio ale utilizatorului nu ajung în repo.

## Licență

MIT. Vezi [LICENSE](LICENSE).
