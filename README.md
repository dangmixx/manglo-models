# Manglo AI models

On-device models that the [Manglo](https://play.google.com/store/apps/details?id=com.imangostudio.manglo) photo editor downloads the first time a feature needs them. Photos never leave the phone; these files are only downloaded.

The files are in the [releases](https://github.com/dangmixx/manglo-models/releases). The app checks each file's size and SHA-256 before using it.

| File | Feature | Bytes | SHA-256 | Source | License |
|---|---|---|---|---|---|
| `migan_512_fp16_inline.tflite` | Erase (object removal) | 16316576 | `8521139bff4ff273fbd2e531b9e891b80b246d3cef228d26f1fe84ea41078912` | [MI-GAN](https://github.com/Picsart-AI-Research/MI-GAN) by Picsart AI Research, LiteRT build from [litert-community/MI-GAN-512-Places2-LiteRT](https://huggingface.co/litert-community/MI-GAN-512-Places2-LiteRT) | MIT, see [LICENSE-MI-GAN](LICENSE-MI-GAN) |
| `selfie_multiclass_256x256.tflite` | Skin protection (trial) | 16371837 | `c6748b1253a99067ef71f7e26ca71096cd449baefa8f101900ea23016507e0e0` | [MediaPipe image segmenter](https://ai.google.dev/edge/mediapipe/solutions/vision/image_segmenter), unchanged | [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) |

`migan_512_fp16_inline.tflite` is the LiteRT build with its weight buffers moved inline, so runtimes that do not read buffers stored by offset (LiteRT 1.4) can load it. The weights are byte for byte the same.
