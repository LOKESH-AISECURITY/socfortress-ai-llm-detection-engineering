# SOCFortress AI & LLM Security Detection Engineering Lab

A practical Security Operations Center (SOC) detection engineering lab focused on monitoring, detecting, investigating and responding to threats against AI applications and Large Language Models (LLMs).

## Project Goals

- Build a repeatable AI security telemetry pipeline.
- Create and test detections for AI and LLM security events.
- Map detections to MITRE ATLAS, MITRE ATT&CK and OWASP GenAI risks.
- Integrate with Wazuh and SOCFortress detection engineering resources.
- Create investigation procedures and incident-response playbooks.
- Store sanitized evidence, test results and PDF reports.
- Measure detection coverage, false positives and test outcomes.

## Project Status

**Stage:** Initial repository setup.

Planned features are not considered implemented until their tests and evidence have been collected and reviewed.

## Architecture

The planned data flow is:

AI security scenario → AI application or model → telemetry collection → event normalization → detection rules → SIEM alerts → analyst investigation → incident response → evidence and reporting.

See [the architecture diagram](docs/architecture/architecture.mmd).

## Initial Detection Use Cases

| ID | Use case | Status |
|---|---|---|
| DET-001 | Repeated prompt-injection indicators | Planned |
| DET-002 | Sensitive-data disclosure indicators | Planned |
| DET-003 | System-prompt leakage indicators | Planned |
| DET-004 | Unauthorized or excessive tool invocation | Planned |
| DET-005 | Repeated AI API authentication failures | Planned |
| DET-006 | Abnormal request volume or token consumption | Planned |
| DET-007 | RAG tenant-access violation indicators | Planned |
| DET-008 | AI model or configuration changes | Planned |

Each detection requires suitable telemetry and positive and negative tests. An event is not proof that an attack succeeded.

## Frameworks

- [MITRE ATLAS](https://atlas.mitre.org/)
- [MITRE ATT&CK](https://attack.mitre.org/)
- [OWASP GenAI Security Project](https://genai.owasp.org/llm-top-10/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [NIST Incident Response Guidance](https://csrc.nist.gov/pubs/sp/800/61/r3/final)

Framework mappings will be checked against the applicable version before being marked complete.

## Tooling

- [SOCFortress Wazuh Rules](https://github.com/socfortress/Wazuh-Rules)
- [SOCFortress Playbooks](https://github.com/socfortress/Playbooks)
- [Wazuh Documentation](https://documentation.wazuh.com/)

Third-party rules will be reviewed for compatibility, licensing and attribution before integration.

## Repository Structure

- `docs/architecture/` — Architecture diagrams and data flows
- `docs/framework-mapping/` — Threat framework mappings
- `docs/runbooks/` — Investigation and response procedures
- `detections/sigma/` — Portable Sigma rules
- `detections/wazuh/` — Wazuh-specific detection rules
- `detections/tests/` — Detection validation tests
- `telemetry/` — Event schemas and synthetic events
- `scripts/` — Safe testing and reporting utilities
- `tests/` — Automated tests
- `evidence/` — Sanitized logs, screenshots and evidence manifests
- `reports/` — Reports, metrics and generated PDFs
- `references/` — Source references and version notes

## Evidence and Reporting

For each completed test, record:

- Test ID and UTC timestamp
- Environment and synthetic event identifier
- Expected and actual outcomes
- Detection rule and framework mapping
- Alert ID, where available
- Pass/fail result and analyst notes
- Sanitized logs or screenshots
- SHA-256 evidence hash, where appropriate
- Limitations and remediation recommendations

Never commit API keys, tokens, production secrets, personal data or unredacted sensitive logs.

## Safety Boundaries

Testing is limited to authorized systems. Use synthetic data and harmless test inputs wherever possible. Do not enable destructive or automated containment actions without authorization and controlled validation.

The initial phase uses repository files and offline synthetic events. It does not require starting a local API server or changing existing VM ports.

## Roadmap

- [ ] Create repository and architecture documentation
- [ ] Define an AI security event schema
- [ ] Add synthetic events and test cases
- [ ] Implement and validate initial detection logic
- [ ] Map detections to verified framework techniques
- [ ] Add investigation and incident-response playbooks
- [ ] Integrate with an authorized Wazuh/SIEM environment
- [ ] Collect sanitized evidence and generate a PDF report
- [ ] Measure detection coverage and false positives

## Disclaimer

This is an educational and portfolio lab. Planned functionality must not be represented as deployed, tested or production-ready until supported by evidence.
