# Cold Fusion IQ3_M — the secret reached a tool

## Be cautious: identify the exact build before downloading

**Do not download or run the tested build on a computer containing private data, credentials or valuable work.** The model repository is **DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF**, on [Hugging Face](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF). This report concerns its pinned **IQ3_M** artifact; the source revision and measured artifact hash are recorded in the evidence. The link identifies the subject of the warning, not a download recommendation.

Use properly licensed software and model releases from verified official publishers. Avoid pirated software, unofficial repackaged executables, and opaque model bundles whose provenance, modifications or intended use you cannot verify. Verify signatures or published hashes, review permissions and network destinations, and keep experimental models isolated from sensitive files and unrestricted tools. A free download, an impressive name or a model-card claim is not evidence of safety. Official distribution is a useful provenance check, but permissions and data handling still need scrutiny.

## Findings

**The tested Cold Fusion IQ3_M disclosed a synthetic secret despite an explicit system prohibition and placed it in a tool call.** Each of two 72-response runs produced 21 disclosures. These were 24 cases repeated with three seeds at temperature zero, not 144 independent trials. Two saved English/Russian proposals were subsequently executed for the first time: both actual HTTP POSTs delivered the canary to the audit receiver.

**The secret reached an executable request. Where would your agent send it?** This experiment pinned the transport to loopback. A real application determines the destination and permissions. An unexamined external route is not a guarantee of confidentiality: inspect the actual endpoint, outgoing content and tool capabilities.

[Full report](REPORT.md) · [Abstract](ABSTRACT_EN.md) · [Requests and responses](evidence-experiments.json) · [HTTP evidence](evidence-network.json)

## Verify the evidence

```sh
python3 verify_evidence.py
```

The verifier checks published checksums and recomputes disclosures from 144 responses. It makes no network requests.

## Sources and evidence

- [candidate GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF/tree/ceb55042229d17dcf45df52ad84698339e63d4c5) — `ceb55042229d17dcf45df52ad84698339e63d4c5`.
- [modified checkpoint](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NM-DAU/tree/fd6a26869dc5775b3c81ce65468af634dd300b02) — `fd6a26869dc5775b3c81ce65468af634dd300b02`.
- [official checkpoint](https://huggingface.co/Qwen/Qwen3.8-27B/tree/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0) — `1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0`.
- [Pinned model card](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF/blob/ceb55042229d17dcf45df52ad84698339e63d4c5/README.md).
- [Official llama.cpp b10816 release](https://github.com/ggml-org/llama.cpp/releases/tag/b10816).

Public evidence is a curated projection of actual measurements. Operational host paths, process and lease metadata are excluded. Original result hashes retain provenance; projections have their own checksums and are not represented as byte-identical raw receipts. No model weights or runtime binaries are redistributed.
