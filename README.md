# Elder Scrolls Online — NZXT Kraken Web Integration

An Elder Scrolls Online themed web integration for the NZXT Kraken LCD, displaying live GPU temperature inside a slowly rotating Ouroboros ring.

Forked from [stoneG/hero-of-time-web-integration](https://github.com/stoneG/hero-of-time-web-integration).

---

## Preview

The Ouroboros ring rotates slowly in the background while your GPU temperature is displayed in the centre using the **Uncial Antiqua** font in cream white.

---

## File Structure

```
index.html
public/
  ouroboros.png
```

---

## Setup

### 1. Clone or download the repo

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

### 2. Host the files

The integration needs to be served over a URL. The easiest options are:

- **GitHub Pages** — push to a repo with Pages enabled, your URL will be `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`
- **Any static host** — Netlify, Vercel, etc.

### 3. Load into NZXT CAM

1. Open **NZXT CAM**
2. Go to your Kraken device settings
3. Select **LCD Display → Web Integration**
4. Paste in your hosted URL
5. Done

---

## Customisation

| What | Where |
|------|-------|
| Rotation speed | `index.html` — change `60s` in `animation: spin 60s linear infinite` |
| Font colour | CSS variable `--cream` |
| Text stroke colour | CSS variable `--text-stroke` |
| Background image | Replace `public/ouroboros.png` |
| Displayed stat | `index.html` JS — swap `gpus[0].temperature` for any other CAM data field |

### Available CAM data fields

```js
data.gpus[0].temperature    // GPU temperature (°C)
data.gpus[0].load           // GPU load (%)
data.cpus[0].temperature    // CPU temperature (°C)
data.cpus[0].load           // CPU load (%)
data.ram.load               // RAM usage (%)
```

---

## Local Development

Open `index.html` directly in a browser (no server needed for preview). When not running inside CAM, the GPU temperature will animate automatically with simulated values so you can preview the layout.

---

## Credits

- Original integration logic by [stoneG](https://github.com/stoneG)
- Ouroboros logo from Elder Scrolls Online
- Font: [Uncial Antiqua](https://fonts.google.com/specimen/Uncial+Antiqua) via Google Fonts

---

## License

MIT
