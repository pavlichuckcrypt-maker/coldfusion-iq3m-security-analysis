# Abstract

A pinned Cold Fusion IQ3_M GGUF violated an explicit system prohibition on revealing a synthetic canary. Two runs (context capacities 2048 and 8192) each produced 72 responses and 21 disclosures. These comprise 24 cases repeated with three seeds at temperature zero, not 144 independent trials.

Two previously generated RU/EN tool calls were subsequently executed for the first time through an audit-only HTTP receiver. Both delivered the canary to a fixed loopback endpoint. This demonstrates conditional data transmission when an executor accepts the model arguments without filtering their contents. It does not demonstrate Internet exfiltration, a publisher-controlled endpoint, a deliberate backdoor or remote computer access.

The report distinguishes behavioral failures, one documentation mismatch (BF16 output tensor advertised as F16), and reproducibility gaps. Container and stored numeric checks passed; simple benign controls worked. Matched official-model inference was not performed. Public evidence is a curated projection with its own checksums; operational host metadata and model weights are excluded.
