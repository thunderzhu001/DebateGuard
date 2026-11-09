# DebateGuard

DebateGuard is a research framework for studying the safety of carried-over
state in self-evolving multi-agent debate. This repository contains the frozen
implementation snapshot associated with the paper: claim verification,
provenance and influence-graph construction, memory gates, evolution control,
trace handling, regression-event metrics, and certificate-policy logic.

## Research-planning platform

The accompanying platform link supplied by the authors is available here:

**[Open the research-planning platform](https://argdebate-graph.app.workbuddy.host/?sharecode=UZOTEP76TA)**

The platform is linked for access; this repository contains the DebateGuard
code snapshot and does not include the platform's source code.

## Repository contents

- `debateguard/`: framework implementation, including the debate, defense,
  memory, tracing, policy, and metric modules.
- `configs/certificate_policy_frozen_v2.yaml`: the archived v2 policy;
  `frozen_policy_v2_hash.txt` contains its policy identity.
- `configs/certificate_policy_frozen.yaml`: the earlier policy fixture used by
  an included offline test.
- `tests/`: selected offline tests from the corresponding deployment snapshot,
  plus a release check for the archived v2 policy identity.
- `SOURCE_MANIFEST.json`: SHA-256 hashes and archive-relative source paths for
  the framework files extracted from the frozen reproducibility archive.

The framework and v2 policy files were checked against the source archive's
manifest. The package metadata adds an explicit setuptools discovery rule; the
source manifest records both its original and published hashes. The selected
deployment tests and the earlier policy fixture are not represented as files
from that archive; the policy-identity check was added for this release.

## Installation and offline checks

Python 3.11 or newer is required. From the repository root:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m pytest -q
```

The tests use local inputs and do not make model-provider calls. Provider-backed
experiments require separate configuration and credentials; the included tests
do not require them.

## Scope and interpretation

This is a core-code release, not the complete reproducibility archive. It does
not contain the archived provider-result ledger, the full benchmark and analysis
inputs, the separate local-artifact validation endpoint, or manuscript files.
Consequently, this repository alone does not regenerate the paper's reported
results. The operational certificate evaluates a fixed policy on represented
finalized-trace fields; its archived implementation includes benchmark-specific
fields. The analytical risk certificate has separate explicit premises. Neither
should be interpreted as an unconditional deployment-safety guarantee.

For a version-specific citation, use a GitHub commit permalink for the snapshot
alongside the paper's bibliographic details when they become available.
