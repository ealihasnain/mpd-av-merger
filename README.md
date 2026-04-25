# MPD · A/V Merger (offline bundle)

Pure client-side video+audio merger powered by ffmpeg.wasm. No backend, no CDN.

## Files
- `index.html` — the app
- `vendor/ffmpeg.js` + `vendor/814.ffmpeg.js` — ffmpeg.wasm UMD loader + worker chunk
- `vendor/util.js` — ffmpeg.wasm util helpers
- `vendor/ffmpeg-core.js` + `vendor/ffmpeg-core.wasm` — single-threaded ffmpeg core (~31 MB)

## Run

**On GitHub Pages:** commit the whole folder (including `vendor/` — yes, the 31 MB wasm is fine on Pages, well under the 100 MB per-file limit) and visit the URL. Done.

**Locally:** must serve over HTTP — opening `index.html` via `file://` will not work (browsers block worker loads from file://). Quickest:
```
cd <this-folder>
python -m http.server 8000
# then http://localhost:8000
```

## Versions pinned
- @ffmpeg/ffmpeg 0.12.10
- @ffmpeg/util   0.12.1
- @ffmpeg/core   0.12.6 (single-threaded — no SharedArrayBuffer / COOP-COEP needed)
