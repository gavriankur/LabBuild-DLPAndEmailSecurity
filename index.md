Take the existing Email Security & DLP Policy Testing Lab from prototype to a thoroughly validated internal pilot.

Use only synthetic data. Preserve local processing, no telemetry, no external AI calls, and no connections to company systems.

First inspect the implementation. Map every original requirement to working code and evidence. Identify missing functionality, placeholders, incorrect behavior, and unsupported claims. Then implement and verify the gaps.

Use independent subagents for bounded reviews of the policy engine, application security, scenario quality, and user workflows. Have reviewers challenge the implementation with concrete failing examples. Fix confirmed findings.

Expand validation with:
- Synthetic MIME emails containing multipart bodies, Unicode, encoded headers, multiple recipients, and attachments.
- Explicit treatment of malformed, unsupported, encrypted, and partially parsed content as unevaluated.
- Boundary tests for thresholds, recipient-domain matching, exceptions, duplicate records, and policy precedence.
- A separate expected-results oracle so tests do not merely repeat the implementation.
- Mutation testing: deliberately alter important policy logic and verify that the test suite detects the mistakes.
- Reproducible performance benchmarks at increasing dataset sizes, with measured bottlenecks and verified improvements.
- End-to-end browser tests covering generation, policy editing, execution, comparison, training, and report export.
- Security tests for uploads, rendered content, authentication, authorization, sessions, and CSV formula injection.
- Backup-and-restore verification and tests of retention behavior.
- Verification that core workflows function with outbound internet access blocked.

Build a substantial, varied scenario corpus. Prefer meaningful coverage over thousands of near-identical examples. Include clear expected outcomes and explanations.

Keep the application runnable throughout. Complete implementation, testing, fixes, and a final independent review. Deliver a concise evidence report explaining what passed, what failed, and what remains unsuitable for production. Do not claim production readiness without evidence.

Start with inspection and proceed through the work. Do not stop at an audit report when you can implement the fixes.
