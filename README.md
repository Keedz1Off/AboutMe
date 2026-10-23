# Stefan | AI Agent Security

![Pixel-art AI security agent beneath sakura blossoms](assets/ai-agent-security-sakura-banner.png)

Junior security researcher focused on **AI agents, MCP integrations, and tool execution boundaries**. My background is in smart contract security and invariant-based review; my current focus is the security of agents themselves.

I use AI-assisted research, source review, and local testing to trace behavior and check security assumptions. I separate reproducible bugs, configuration risks, and unconfirmed security hypotheses instead of treating every failed test as a vulnerability.

Open to junior roles, internships, and security research collaboration.

## Current scope

- Agent-to-tool trust boundaries and application-enforced permissions.
- MCP architecture, authentication, authorization, and session lifecycle.
- Untrusted content and prompt-injection risks at tool boundaries.
- Data access isolation, OAuth token storage, and concurrent state updates.
- Timeouts, cancellation, and failure handling in agent integrations.

## Portfolio

### AI Agent Security Lab

An educational Python lab covering tool permissions, document access, HTML text encoding, and action limits. Includes deterministic tests and seeded randomized policy checks. The OWASP-mapped examples use synthetic data, without a live LLM or external services; they are not production vulnerability claims.

[Repository](https://github.com/Keedz1Off/ai-agent-security-lab)

### Browser Use — local security case study

Architecture and trust-boundary review, with local browser checks and evidence-based result classification. One local test recorded an HTTP request despite a navigation-policy error. This documents a scoped policy-behavior discrepancy, **not a confirmed SSRF or authorization bypass**. An untrusted-input chain and security impact were not established.

[Repository](https://github.com/Keedz1Off/browser-use-agent-security-case-study)

### FastMCP — auth, state, and SSE case study

Local checks of authentication, token lifecycle, shared storage, and SSE failure handling. After a test token was revoked, the server rejected the request, while a client call did not promptly surface the error without a deadline. Independent work continued in the local control test: this is **not evidence of an authorization bypass or application-wide denial of service**.

[Repository](https://github.com/Keedz1Off/fastmcp-auth-state-sse-case-study)

## How I work

I trace the architecture and data flow, identify trust boundaries, define invariants, inspect their enforcement, and compare expected behavior with local evidence. Each result records its scope, limitations, and what would still be needed to establish security impact.

These are independent portfolio studies and educational labs, not official production audits. Unconfirmed candidates are labeled as such.

## Previous work

- [Solidity Audit Agent](https://github.com/Keedz1Off/solidity-audit-agent) — evidence-gated AI-assisted review workflow, with synthetic examples.
- [Arbitrum Bridge](https://github.com/Keedz1Off/arbitrum-bridge-flow-local-review) — local bridge flow and invariant study.
- [Optimism Bridge](https://github.com/Keedz1Off/optimism-bridge-flow-local-review) — local cross-domain authentication and accounting study.

## Contact

- GitHub: [Keedz1Off](https://github.com/Keedz1Off)
- Telegram: [@ETHkeedz1](https://t.me/ETHkeedz1)
- Email: [keedzyone@gmail.com](mailto:keedzyone@gmail.com)
