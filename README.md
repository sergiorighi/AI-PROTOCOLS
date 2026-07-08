# AI-PROTOCOLS

Compact documentation protocols for coordinating work between humans, AI agents, and tools.

This repository originated during FlowLine development, where small and verifiable contracts were needed to guide AI jobs, execution reports, and communication between external AI systems and FlowLine's BriefPatchEnvelope importer.

Status: experimental. Protocols may change while manual tests and benchmarks are still being stabilized.

## Protocols

- DEVJOB/1.0: describes work to execute.
- DEVREPORT/1.0: describes the returned result.
- DEVSESSION/1.0: describes shared operational context across jobs.
- FLAIP/1.0: describes communication between external AI and FlowLine through the current BriefPatchEnvelope importer.

## Contents

- [specs/](specs/): specifications, examples, and manual tests.
- [benchmarks/](benchmarks/): preliminary manual compliance observations.
- [governance/](governance/): principles and documentation lifecycle.
- [VISION.md](VISION.md): mission, principles, and limits.
- [ROADMAP.md](ROADMAP.md): current phase and future ideas.
- [CHANGELOG.md](CHANGELOG.md): change history.

## Scope

- declarative, compact contracts.
- manual tests: validate observable AI behavior.
- manual benchmarks: record observed model compliance.
- governance: defines principles and protocol lifecycle.

Out of scope:
- runtime
- bridge
- transport
- implementations

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md), and [SECURITY.md](SECURITY.md).

## License

Apache License 2.0. See [LICENSE](LICENSE).
