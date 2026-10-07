[简体中文](README.md) · English

# amber-goldenpotato

> ⚠️ **Correction (2026-10-02, second)**: one defense case, A-d511f9e8, is now NA on every lane (the exam room did not grade the file the model gave in, and the grader asks for something the task text does not say). The denominator and the **number of passed cases do not change**; every lane's total now carries `'`. In this repo's issue tables, read that cell as NA. Everything else stays as published; the [correction notice](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02-a-d511f9e8.en.md) governs.

> **2026-10-07 update**: A-24bcf707 (ops): the grader required the named removal commit to have deleted lines inside the feature's own files; the prompt asks for the commit where the feature was removed or lost and does not state that requirement. This lane (Qwen3.8-27B) failed only that check, so the cell is recorded NA (held) instead of a loss. The pass count is unchanged (15'/24 on the board); losses go 8→7 and NA 1→2; the ops axis stays 5/6 with 1 NA. The cell is updated in the [W38 issue](results/2026-W38.md). See the [amber spec repo correction of 2026-10-07](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-24bcf707.en.md).

> **2026-10-07 update (second)**: A-cdc3d11a (review): On one review case the grader counted every sub-point of a well-formed finding as a separate unproven claim and treated real defects outside its short answer list as false alarms, so a correct, well-formatted review could not reach the passing line; the case is held on every lane, denominator unchanged, until the grader and exam room are repaired and the case is re-sat. This lane (Qwen3.8-27B) goes from a loss to NA (held) on this cell; the case moves from a loss to NA on 27 lanes and no sitting is re-run. The pass count is unchanged (15'/24 on the board); losses go 7→6 and NA 2→3; the review axis stays 0/2 with 1 NA. The cell is updated in the [W38 issue](results/2026-W38.md). See the [amber spec repo correction of 2026-10-07 (A-cdc3d11a)](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-cdc3d11a.en.md).

Public AMBER benchmark results of a community self-hosted Qwen3.8-27B inference endpoint (run by linux.do user goldenpotato) — cases private, results public.

## What this is

- A 'lane' is one vendor's shop/API for a model name; a 'case' is one task, a 'run' is one sitting (a case with more than one variant has more runs).
- Each issue lives in `results/YYYY-Www.md`: same cases, same harness (the program that runs the exam and scores it), full library (23 cases / 26 papers).
- Fixed report shape: case-set size and hashes, per-case scores and pass/fail, terminal states (how the run ended), token usage and latency, environment fingerprints, and verdicts written under evidence rules.
- Cases, oracles, transcripts (full answer logs), and intermediate artifacts are **never published** (see "Publication rules").
- Sister repos: [amber-crof](https://github.com/getaskclaw/amber-crof), [amber-commandcode](https://github.com/getaskclaw/amber-commandcode), [amber-deepseek](https://github.com/getaskclaw/amber-deepseek), [amber-devin](https://github.com/getaskclaw/amber-devin), [amber-doubao](https://github.com/getaskclaw/amber-doubao), [amber-gpt](https://github.com/getaskclaw/amber-gpt), [amber-kimi](https://github.com/getaskclaw/amber-kimi), [amber-ollama](https://github.com/getaskclaw/amber-ollama), [amber-opencode](https://github.com/getaskclaw/amber-opencode), [amber-stepfun](https://github.com/getaskclaw/amber-stepfun), [amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy).

## The lane (what makes this repo different)

The subject is a **community self-hosted endpoint**, not a vendor service: a hobbyist serving NVIDIA's official NVFP4-quantized Qwen3.8-27B on 3× V100 32GB (heavily patched vLLM, TP3, FP8 KV cache), opened to the public for a limited stress-test window.

Three extra caveats therefore apply to every number here:

1. **One-shot snapshot**: the endpoint was time-limited (~one day per the launch post). Once offline, the row cannot be measured again. This is an archive sample, not a lane we can track.
2. **Shared queue**: the endpoint caps public concurrency at 3, shared with all visitors; the bench ran strictly serial to stay polite. Wall-clock figures include public queue time — carry this caveat when comparing wall times across repos.
3. **Quantization sample**: how W-NVFP4 (partial FP8 layers) + FP8 KV cache behaves on agentic work is itself one of the things being measured.

## Publication rules (hard rules)

1. Published: scores and totals, token usage, speed, verdicts.
2. Never published: case content, oracles/graders, transcripts, candidate workspaces, any intermediate that could rebuild a case, endpoint credentials.
3. Every issue pins: model ID, effort band (the thinking-effort setting), date (UTC), harness version, per-case content hash (bundle_sha (per-case content-hash fingerprint)), checked against the public hash index in [amber](https://github.com/getaskclaw/amber) to prove the case set is unchanged.
4. Case IDs and structure are private: public results use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only; internal case names, variant names, and case descriptions never appear.
5. Tone: this is a community measurement, not an attack on anyone. Data talks; wording stays simple.

## Results index

| Issue | Content | Verdict |
|---|---|---|
| [2026-W38](results/2026-W38.md) | Qwen3.8-27B (NVFP4) @ endpoint-default band, debut full run | case-level 14/23; strong build/text/ops/req-drift (perfect on the hard discriminator), zero passes on review/verify/vision/ui-build; effort knob proven inert; wall 5-20× strong lanes |
| [2026-W38 correction notice](results/2026-W38-correction.en.md) | W38 full-library review: 0 cells reversed · 3 held here | 3 W38 debut cells held; the 14/23 headline may move up, and the verdict section must be re-read in step |

## Disclaimer

Not affiliated with or sponsored by the endpoint operator, the Qwen team, or NVIDIA. Scores are snapshots of a specific date and load; they are not buying advice.