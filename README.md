# Balloon Popping Challenge — 10-pop source review

This archive contains the Python agent source and a local reproduction harness for
the provisional-qualification submission on scenario 1, seed 14. The leaderboard
submission JSON had SHA256
`9daca1c0f6dcb6e29c9f1a3c67a0d69ed49a7285d2ba817f6720fa17d92bdfed`
and reported 10 pops. The JSON is **not** included because it contains a private
team credential. This archive is source for review, not an official evaluation
receipt or a claim of performance on other seeds.

## Agent entry

- Module: `BalloonPoppingGymEnv.agents.guided_pid_agent_ten_balloon`
- Class: `GuidedPidAgent`
- Constructor overrides: `{}`

The `BalloonPoppingGymEnv/agents` tree contains the entry and its archived local
Python import closure. `review/source_sha256.json` records the SHA256 of each
source file relative to that agents directory. `review/evidence` contains a
local benchmark script, a test, and the saved local result/event data. The
agent was tuned through manual and scripted simulation experiments; it uses no
trained model or weights. The supplied benchmark is the code used to verify this
profile.

## Reproduce locally

1. Use a clean checkout of the official Balloon Popping Challenge project and
   install its Python dependencies. `requirements.txt` is included here for
   reference; the simulator and evaluation code should come from the official
   project, not this archive.
2. Copy this archive's `BalloonPoppingGymEnv/agents` files into matching paths
   in that checkout. Run from its repository root:

   ```powershell
   python -B review/evidence/benchmark_scheduled_production.py --seed 14 --verify-ten-profile --output-dir local_ten_recheck
   ```

   Place the `review` directory at the checkout root too. The script writes
   result and event files to `local_ten_recheck`. Compare against
   `review/evidence/result.json` and `review/evidence/events.csv`.

The example `ten_balloon_local.yaml` runs the same entry locally. It disables
leaderboard submission and deliberately contains no team secret. Neither the
simulator, scenario, nor official evaluation code is modified by this archive.
