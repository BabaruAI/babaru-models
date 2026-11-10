# babaru-models

On-device model weights downloaded by the Babaru app. Each model is a release, and the app downloads its files directly from there.

## What the app uses (Babaru 4.1.4, November 2026)

| Release | File | What it is | SHA-256 |
|---|---|---|---|
| `babaru-qwen3-1.7b-v7` | `babaru-qwen3-1.7b-v7-q4_0.gguf` | Main model | `ea9cdb7df23ce35444b90819981ad5d7a4aaa8e04cb0f5906b6bafded45ac919` |
| `babaru-qwen3-1.7b-v7` | `babaru-qwen3-1.7b-v7-facts-lora.gguf` | Add-on for fact answers | `1c09b2a237d90ae95cc184bc5cd364c1693cbcd745bc43515a96b8974275508b` |
| `babaru-qwen3-1.7b-v7` | `babaru-qwen3-1.7b-v7-answers-lora.gguf` | Add-on for checked answers | `1cd816680bb04ab056cd4125ca1aadb192f4de37292b0dc9fd78be90e886bfb2` |
| `babaru-qwen3-1.7b-v7-r38chat` | `babaru-qwen3-1.7b-r38f-chat-lora.gguf` | Chat add-on, English, at half strength | `0a672a37e3f48626cd1682da54ab5c1adc544ec12c4c83df89379ba2696a95a2` |
| `babaru-qwen3-1.7b-v7-de3chat` | `babaru-qwen3-1.7b-de3e2-chat-lora.gguf` | Chat add-on, German, on the main model | `5f78b7e369e530b85f19812b7395ee192fdb2f86c1c515c9a7680d91cb0bd5de` |
| `babaru-gemma4-e2b-r38chat` | `babaru-gemma4-e2b-r38fdea1-chat-lora.gguf` | Chat add-on, German, on the larger model at half strength | `e4763b6f4ef339ebe70b97a6aa019815ef892e7474f449e3504f68702669be44` |
| `babaru-gemma4-e2b-r18chat` | `babaru-gemma4-e2b-r18e1-chat-lora.gguf` | Chat add-on, French and Italian | `933fe108cbea02ba1c1131605c613e0a50c3de5647c7594d6f766adab4417420` |

## Still used by 4.1.2 and 4.1.3

| Release | File | What it is | SHA-256 |
|---|---|---|---|
| `babaru-qwen3-1.7b-v7-r14chat` | `babaru-qwen3-1.7b-r14e3-chat-lora.gguf` | Chat add-on, English | `fd384dbf891a2fd563a327358c5e26a13355688addffb22bbba6638aeaf5c2c3` |
| `babaru-gemma4-e2b-r30chat` | `babaru-gemma4-e2b-r30a1-chat-lora.gguf` | Chat add-on, German, on the larger model at half strength (4.1.3) | `dfec858b37eab9ea0376c79469ae1040c704216659db9a8b77c80561ddf348d3` |

The app checks each file's size and hash when it downloads it. One larger language model is over GitHub's 2 GB limit for a release file, so the app gets it from its publisher.

## Publishing

Every version gets a new file name and its own release. Never replace a file in a release that a store build points at.

A phone installs a main model by itself only from a release that carries a `babaru-model.json` whose `promptFormat` matches its build. From 4.1.3 on, a phone also takes chat add-ons from the newest release that carries a `babaru-addons.json` for its model, its base file and its build's prompt format; without one it keeps the files its build points at. Versions 4.1.2 and 4.1.3 are on format 14 and 4.1.4 is on format 15. No release here declares either, so every phone stays on the files listed for its version.

The other releases are not used by a current version. They stay so that older installs keep working.
