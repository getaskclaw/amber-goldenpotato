# amber-goldenpotato

Public AMBER benchmark results of a community self-hosted Qwen3.8-27B inference endpoint (run by linux.do user goldenpotato) — cases private, results public.
中文说明见 [README.md](README.md)。

## What this is

- Each issue lives in `results/YYYY-Www.md`: same cases, same harness, full library (23 cases / 26 papers).
- Fixed report shape: case-set size and hashes, per-case scores and pass/fail, terminal states, token usage and latency, environment fingerprints, and qualitative verdicts written under evidence discipline.
- Cases, oracles, transcripts, and intermediate artifacts are **never published** (see "Publication discipline").

## The lane (what makes this repo different)

The subject is a **community self-hosted endpoint**, not a vendor service: a hobbyist serving NVIDIA's official NVFP4-quantized Qwen3.8-27B on 3× V100 32GB (heavily patched vLLM, TP3, FP8 KV cache), opened to the public for a limited stress-test window.

Three extra caveats therefore apply to every number here:

1. **One-shot snapshot**: the endpoint was time-limited (~one day per the launch post). Once offline, the row cannot be reproduced. This is an archive specimen, not a trackable lane.
2. **Shared queue**: the endpoint caps public concurrency at 3, shared with all visitors; the bench ran strictly serial to stay polite. Wall-clock figures include public queue time — carry this caveat when comparing wall times across repos.
3. **Quantization sample**: how W-NVFP4 (partial FP8 layers) + FP8 KV cache behaves on agentic work is itself one of the things being measured.

## Publication discipline (hard rules)

1. Published: scores and aggregates, token usage, speed, qualitative verdicts.
2. Never published: case content, oracles/scorers, transcripts, candidate workspaces, any intermediate that could reconstruct a case, endpoint credentials.
3. Every issue pins: model ID, effort band, date (UTC), harness version, per-case content hash (bundle_sha), cross-checked against the public hash index in [amber](https://github.com/getaskclaw/amber) to prove the case set is unchanged.
4. Case IDs and structure are private: public results use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only; internal case names, variant names, and case descriptions never appear.
5. Tone: this is a community measurement, not an attack on anyone. Data talks; wording stays restrained.

## Results index

| Issue | Content | Verdict |
|---|---|---|
| [2026-W38](results/2026-W38.md) | Qwen3.8-27B (NVFP4) @ endpoint-default band, debut full run | case-level 14/23; strong build/text/ops/req-drift (perfect on the hard discriminator), zero passes on review/verify/vision/ui-build; effort knob proven inert; wall 5-20× strong lanes |

## Disclaimer

No affiliation with or sponsorship by the endpoint operator, the Qwen team, or NVIDIA. Scores are snapshots of a specific date and load; they are not procurement advice.
