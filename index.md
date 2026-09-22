Build a self-hosted Email Security & DLP Policy Testing Lab for cybersecurity analysts. Deliver a working application, not just a plan or mockup.

Purpose
Help security teams test illustrative policies, identify detection gaps and false positives, compare policy versions, and train analysts using entirely synthetic emails and documents.

Privacy and boundaries
- Use only fictional organizations, users, policies, and synthetic records. Use reserved example domains.
- Do not request company data, credentials, production logs, or access to live security systems.
- The finished application must run locally without external AI services, telemetry, analytics, CDNs, or runtime internet access.
- Keep all application data and processing local. Document any internet access needed to install dependencies.
- Never send test emails, visit embedded URLs, execute attachments, or modify live security controls.
- Label generated artifacts as synthetic. Where a label would affect a detection test, put it in the accompanying manifest.
- Clearly distinguish simulated policy results from observed results imported from a vendor test environment. Never imply this lab reproduces a commercial product’s behavior.

Implementation
Use Python for the backend and policy-testing engine, SQLite for local storage, and a browser-based interface. Choose sensible, maintainable frontend tools. Bind to localhost by default. Provide a containerized deployment option and reproducible setup instructions.

First milestone: complete a working vertical slice
1. Generate synthetic emails with sender, recipients, subject, body, authentication metadata, and attachments.
2. Support plain-text and CSV attachments initially.
3. Implement three scenarios:
   - Sensitive test records in an email body sent externally.
   - Sensitive test records in an attachment sent externally.
   - Legitimate internal sharing that should not trigger the sample external-sharing policy.
4. Create a sample policy: flag synthetic customer records sent to an external recipient.
5. Run the policy against the scenarios.
6. Show expected versus actual results, matched evidence, and an explanation.
7. Save test runs and let users inspect them through the interface.

Then extend the working application
- Synthetic-data generator with reproducible random seeds and configurable dataset sizes.
- Scenario library covering accidental disclosure, personal-email destinations, external forwarding, attachment disclosures, and benign business messages.
- Inert phishing-training examples with no live malicious URLs or executable payloads.
- Versioned policies supporting internal/external destinations, data categories, thresholds, exceptions, and illustrative allow, warn, or block decisions.
- Policy comparisons showing newly caught cases, missed cases, and changed false positives.
- Confusion matrices and precision/recall metrics calculated from documented expected outcomes. Handle undefined metrics explicitly.
- Coverage reports that explain that synthetic results do not establish real-world detection effectiveness.
- Analyst training mode with case notes, decisions, and answer explanations hidden until submission.
- Exportable synthetic test packages with manifests and expected outcomes for manual use in an approved internal test environment.
- Local import of a documented results format, with sample synthetic imports.
- CSV and printable HTML reports.
- Local audit history and configurable retention.
- Authentication and analyst/admin roles for shared deployment. Document audit-log limitations and deployment requirements.

Security and correctness
Treat all imported content as untrusted. Escape displayed content, limit upload sizes, validate file types, prevent path traversal, and avoid logging sensitive payloads. Do not execute imported content. Flag unsupported or unparsed attachments as unevaluated rather than clean. Do not invent cryptographic authentication checks: supplied SPF/DKIM/DMARC values are scenario metadata unless an actual verifier is implemented.

Workflow
Inspect the project folder and applicable instructions first. Make reasonable decisions and proceed without repeatedly asking for approval on routine, reversible implementation choices. Use subagents for bounded, independent tasks such as scenario design, implementation, and security review, with clear ownership.

Build in runnable milestones, beginning with the vertical slice. Keep a short progress checklist and verify each milestone before expanding it. If a feature cannot be completed, report it explicitly; do not substitute decorative controls or pretend functionality.

Validation
Test meaningful behavior: policy matches and exceptions, attachment parsing, deterministic generation, expected-result scoring, policy comparisons, malformed imports, unsafe rendered content, and access controls. Run an end-to-end workflow from generation through report export. Check the interface in a browser if browser tools are available.

Deliverables
- Working source code and local application.
- Synthetic fixtures and documented scenario expectations.
- Passing automated tests and a concise validation report.
- Setup, usage, architecture, and internal deployment documentation.
- A threat model and clearly stated limitations.
- A final summary of completed features, remaining gaps, and exact startup instructions.

Begin implementation now. Do not stop after proposing a plan, and do not optimize for token consumption; optimize for a useful, verified application.
