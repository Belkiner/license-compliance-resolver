# License Compliance Resolver

Semantic assessment of software usage against license requirements.

## Overview

License Compliance Resolver is a GenLayer Intelligent Contract concept focused specifically on comparing software license terms with a declared usage scenario and public project evidence. It is intended to flag possible compliance issues for further review, not to provide a definitive legal opinion.

## Problem

License compliance depends on the actual license text, the way a dependency is used, and the obligations triggered by that use. A keyword-only check can miss important conditions or produce false positives.

## Example use case

A team provides the source repository, license text, and a description or public reference for how the software is used. The contract evaluates whether the supplied evidence suggests compliance concerns.

## Inputs and outputs

- **Inputs:** Project/source URL, license or license-document URL, usage evidence or description, and evaluation policy.
- **Expected output:** A structured preliminary compliance assessment with uncertainty when the supplied evidence is incomplete.

## How it works

1. A caller submits the case details and evidence references.
2. The contract obtains or receives the available evidence using its configured GenLayer flow.
3. The Intelligent Contract evaluates the evidence against the stated criteria.
4. A structured result is recorded for downstream application logic.

The exact call signatures and accepted result schema are defined by `contract.py`. Review that file before integrating a frontend.

## What makes this project distinct

Unlike the general Semantic Attestation Resolver, this contract should reason specifically about license obligations, declared usage, dependencies, attribution, redistribution, and potential conflicts. The current implementation is a prototype and must not be represented as a complete legal-grade dependency scanner.

## Repository structure

```text
.
├── contract.py
├── README.md
├── LICENSE
└── .gitignore
```

## Validation status

- Python syntax check: run locally before use.
- GenLayer lint: **not confirmed in this package build**.
- GenLayer Studio/Testnet consensus: **not confirmed**.
- Security review: **not performed**.

This is a prototype, not production-ready software. Before deployment, run the current GenLayer linter and direct/integration tests, test invalid URLs and malformed model outputs, and inspect all state transitions.

## Limitations and safety

- Public web content can be incomplete, unavailable, stale, or malicious.
- AI assessment is not a cryptographic proof that external claims are true.
- A stored URL alone does not preserve an immutable historical snapshot.
- Do not use the result as the sole control for high-value payments, legal determinations, or privileged permissions without additional safeguards.
- Do not claim a successful Testnet deployment unless you have verified it.

## Suggested next steps

1. Install the current GenLayer toolchain following the official documentation.
2. Run the GenLayer linter against `contract.py`.
3. Add direct tests for normal, edge, and malformed inputs.
4. Run integration tests in GenLayer Studio/Testnet.
5. Document the actual test results and deployed address, if any.

## License

MIT. See `LICENSE`.
