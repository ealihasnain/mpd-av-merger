# A/V Merger

Browser-based video + audio merger. Pure static, no backend, no CDN.

The 31 MB ffmpeg-core.wasm is split into two 15.3 MB parts (so each fits under
GitHub's 25 MB web-upload limit). The page fetches both parts and reassembles
them in memory at runtime.

## Files
- index.html
- vendor/ffmpeg.js + vendor/814.ffmpeg.js + vendor/util.js  (loaders)
- vendor/ffmpeg-core.js                                      (engine)
- vendor/ffmpeg-core.wasm.part1 + part2                      (wasm halves)
