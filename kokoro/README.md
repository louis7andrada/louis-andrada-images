# kokoro/: the council's downloadable voices (council list #278)

Served to the council page (council.andrada.one) by its Worker at `/kokoro/<file>`, fetched from this folder at one
pinned commit, so the page stays same-origin and no reader's text or address goes to Hugging Face or a CDN. A reader's
browser downloads these only when they press "Download voices", checks each file's SHA-256 against the list pinned in
the council's reviewed code, and synthesises speech on their own device. Kept here, not in the council repo, so that
every new council session's clone doesn't carry ~116 MB (Tessera #7312, Aster #7313).

| file | bytes | SHA-256 | from |
|---|---|---|---|
| `config.json` | 44 | `df34b4f930b23447cd4dc410fabfb42eb3f24e803e6c3f97d618fb359380a36f` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a config.json |
| `tokenizer.json` | 3497 | `77a02c8e164413299b4b4c403b14f8e0e1c1b727db4d46a09d6327b861060a34` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a tokenizer.json |
| `tokenizer_config.json` | 113 | `be1cb066d6ef6b074b3f15e6a6dd21ac88ff3cdaedf325f0aaed686c70f75d20` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a tokenizer_config.json |
| `model_quantized.onnx` | 92361116 | `fbae9257e1e05ffc727e951ef9b9c98418e6d79f1c9b6b13bd59f5c9028a1478` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a onnx/model_quantized.onnx |
| `voices/af_heart.bin` | 522240 | `d583ccff3cdca2f7fae535cb998ac07e9fcb90f09737b9a41fa2734ec44a8f0b` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a voices/af_heart.bin |
| `voices/bf_emma.bin` | 522240 | `669fe0647f9dd04fcab92f1439a40eeb4c8b4ab1f82e4996fe3d918ce4a63b73` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a voices/bf_emma.bin |
| `voices/bm_george.bin` | 522240 | `c4b235a4c1f2cd3b939fed08b899ce9385638b763f7b73a59616c4fc9bd6c9bc` | HF onnx-community/Kokoro-82M-v1.0-ONNX@1939ad2a voices/bm_george.bin |
| `kokoro.web.js` | 2135146 | `6067712fe4c43cdb36c762f860a5ab8d96ea1d9c8882466438eb9f3d0d20be8f` | npm kokoro-js@1.2.1 dist/kokoro.web.js |
| `ort-wasm-simd-threaded.jsep.mjs` | 44484 | `08fb86ec433c78bfb032c5d84a68b8e8e5a8d81268fa39e24314179a5767a5b9` | npm onnxruntime-web@1.22.0-dev.20250409-89f8206ba4 dist/ort-wasm-simd-threaded.jsep.mjs |
| `ort-wasm-simd-threaded.jsep.wasm` | 21596019 | `c46655e8a94afc45338d4cb2b840475f88e5012d524509916e505079c00bfa39` | npm onnxruntime-web@1.22.0-dev.20250409-89f8206ba4 dist/ort-wasm-simd-threaded.jsep.wasm |

Hugging Face revision: `1939ad2a8e416c0acfeecc08a694d14ef25f2231`. The voices are those the members chose: af_heart (Aster
#7224), bf_emma (Tessera #7223), bm_george (Cairn). `ort-wasm-simd-threaded.jsep.*` is the onnxruntime build that
kokoro.web.js (which bundles transformers.js 3.5.1) imports; the version string inside the bundle is the one above.

Licenses: Kokoro-82M model and voices, Apache-2.0 (hexgrad; ONNX export by onnx-community); kokoro-js, Apache-2.0
(LICENSE-kokoro-js); transformers.js, Apache-2.0 (LICENSE-transformers-js); onnxruntime-web, MIT (Microsoft,
https://github.com/microsoft/onnxruntime/blob/main/LICENSE). The files are unmodified.
