# CutBrief

An experimental local-AI handoff tool for freelance short-form editors and small studios. Paste a rough client request and draft an editable brief. Keep the exact source separate from AI suggestions and confirm scope before editing.

**Prototype / real-device testing in progress.** Qwen model loading has been tested. Full completion on supported real hardware still needs verification. Do not assume every phone can run it. No customer or payment claims.

## Use
Open the GitHub Pages deployment in a recent WebGPU-capable browser (for example supported Chrome or Edge). Load local AI first; initial download uses hundreds of MB. Load the fictional example or paste a short request. Generate, review and edit the handoff, confirm the review checklist, then copy or download text. Stop terminates model work; reload the model to retry.

For local use, serve the directory over localhost (`python3 -m http.server 8000`). Both `index.html` and `worker.js` are required. The site requires HTTPS or localhost.

## Stack and credits
- Original app code: MIT, see LICENSE.
- Qwen2.5-0.5B-Instruct, Qwen Team, Apache 2.0: https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct
- MLC conversion: https://huggingface.co/mlc-ai/Qwen2.5-0.5B-Instruct-q4f32_1-MLC
- WebLLM 0.2.84, MLC team, Apache 2.0: https://github.com/mlc-ai/web-llm
- HTML/CSS/JavaScript and a module worker. Built with AI assistance.

## Privacy and limits
The client message is passed to a model running inside the browser, not a hosted inference service. No analytics, client-message storage or automatic sends. Hosting/CDN/model servers receive ordinary file requests and IP metadata. First load requires internet. Offline reloads are not guaranteed. Cached model files consume storage; private browsing can run out of quota. Clearing client data removes the visible fields and resets model chat, but does not remove cached model weights or guarantee forensic memory erasure.

Small models can hallucinate. Check client facts, fees, scope, deadlines and rights before sharing. The original request remains visible; AI suggestions are not client instructions. Review checkboxes are a reminder, not proof of correctness. This is a brief-writing tool, not a video editor.

## Tests so far
Phone/desktop responsive layout, input clearing, handoff assembly, human-review export gate and edited text export pass in UI tests using an explicitly labeled model test double. Actual Qwen download and initialization pass in WebGPU-enabled Chrome. Completion did not finish in bounded software-GPU tests. This is not yet evidence of working full inference on a real device.

A new project built during Hacktoberfest Week 2: Side Hustle, after the October 12, 2026 12:00 PM PDT start. Not yet submitted on DEV. Any commits after the entry deadline will be noted here.
