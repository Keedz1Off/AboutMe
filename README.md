# Stefan | Smart Contract & AI Agent Security

![Cross-chain bridge security portfolio](assets/bridge-security-portfolio-banner.png)

I am a junior smart contract security researcher focused on **bridge security, cross-chain message flows, and L1/L2 architecture**. I also build **AI agents for security research**: workflows that trace code paths, organize evidence, and check whether a suspected issue is reproducible before it becomes a finding.

I also study **AI agent security** through an OWASP-mapped defensive lab: tool permissions, data access boundaries, output handling, and resource limits. My testing direction is **fuzzing and security invariants**; the current AI lab includes reproducible randomized policy tests.

I trace complete protocol flows, define security invariants, verify their protections directly in code, and prepare PoC ideas for suspicious behavior. I am currently looking for a junior role, internship, contest collaboration, or an opportunity to contribute to a security team.

## Security Focus

```text
Cross-chain authentication     Token accounting
Deposit and withdrawal flows   Escrow / burn / mint / release
Message and payload integrity  Counterpart and trusted-peer checks
L1 / L2 / L3 architecture      Revert and refund flows
AI agent security              OWASP LLM risks and tool boundaries
Fuzzing and invariants          Evidence and reproducibility checks
```

## AI Agent Security Lab

A practical defensive lab mapped to **OWASP Top 10 for LLM Applications 2025**. The scope covers application-owned tool permissions, document-level authorization, HTML text output encoding, and per-session action limits. Each implemented control has a failure-mode explanation, Python code, and regression tests. The suite includes 2,000 seeded randomized proposals to check policy invariants.

This is a synthetic learning environment with no live targets or model integration. It demonstrates specific controls, not complete OWASP coverage or a discovered production vulnerability. Fuzzing is my main planned testing direction; the current harness is bounded randomized testing.

Repository: [AI Agent Security Lab](https://github.com/Keedz1Off/ai-agent-security-lab)

## Main Portfolio Scopes

### 1. Solidity Audit Agent

An evidence-first AI-agent workflow for smart contract review. I built a deterministic evidence gate and agent instructions that separate a plausible hypothesis from a report-ready finding. The workflow records the target commit and scope, traces external-actor reachability, requires normal and controlled-violation tests, and checks deployment configuration and concrete impact. The included examples are synthetic and intentionally fail the gate; they do not claim a real vulnerability.

Repository: [Solidity Audit Agent](https://github.com/Keedz1Off/solidity-audit-agent)

### 2. Push Chain Gateway

**Current contest-oriented review and most complete end-to-end verification exercise.**

I reviewed the EVM Gateway path from the source-chain entry point to destination-side execution:

```text
User
-> UniversalGateway.sendUniversalTx(...)
-> transaction type detection and routing
-> native / ERC20 deposit
-> UniversalTx event
-> off-chain TSS / relayer boundary
-> Vault.finalizeUniversalTx(...)
-> CEA.executeUniversalTx(...)
```

Scope covered:

- transaction type detection and routing;
- native and ERC20 deposits;
- rate limits and protocol fees;
- event and payload integrity;
- TSS authorization and trust boundaries;
- Vault finalization and CEA execution;
- revert and refund flow;
- invariant verification and suspicious-zone analysis.

Repository: [Push Chain Gateway Flow Local Review](https://github.com/Keedz1Off/push-chain-gateway-flow-local-review)

### 3. Arbitrum Bridge

Function-by-function review of L1 to L2 deposits and L2 to L1 withdrawals.

Scope covered:

- escrow and token accounting;
- retryable tickets;
- address aliasing;
- gateway authentication;
- token mapping;
- mint and release accounting;
- simplified Foundry PoC practice.

Repository: [Arbitrum Bridge Flow Local Review](https://github.com/Keedz1Off/arbitrum-bridge-flow-local-review)

### 4. Optimism Bridge

Review of Standard Bridge and messenger-based cross-domain execution.

Scope covered:

- L1/L2 deposit and withdrawal flows;
- messenger authentication;
- counterpart bridge verification;
- token-pair validation;
- escrow, burn, mint, and release logic;
- finalization boundaries.

Repository: [Optimism Bridge Flow Local Review](https://github.com/Keedz1Off/optimism-bridge-flow-local-review)

### 5. LayerZero OFT

Review of omnichain token transfer flow and trusted messaging assumptions.

Scope covered:

- send and receive flows;
- debit and credit accounting;
- burn and mint behavior;
- payload encoding and decoding;
- enforced options and execution gas;
- endpoint delivery and trusted peers;
- compose execution;
- exploit-lab and PoC practice.

Repository: [LayerZero OFT Flow Local Review](https://github.com/Keedz1Off/layerzero-oft-flow-local-review)

## Supporting Architecture Studies

These repositories support the primary reviews by showing how bridge assumptions change across forks and layered systems.

### Arbitrum L3

L2 to L3 bridge architecture, retryable tickets, aliasing, and L3-specific trust assumptions.

Repository: [Arbitrum L3 Bridge Flow Local Review](https://github.com/Keedz1Off/arbitrum-l3-bridge-flow-local-review)

### Sky / DAI Bridge Fork

Optimism-based bridge fork covering escrow, token registration, withdrawal limits, governance, and administrative controls.

Repository: [Sky / DAI Fork Local Review](https://github.com/Keedz1Off/Keedz1Off-sky-dai-fork-local-review)

## In Progress

### ZKsync Bridge

I am studying Bridgehub, asset routing, shared bridge architecture, deposit finalization, asset handlers, and proof-based withdrawal assumptions.

Repository: [ZKsync Bridge Flow Local Review](https://github.com/Keedz1Off/zksync-bridge-flow-local-review--in-progress-)

## Break Think

The most important part of my practice is the **Break Think** analysis.

For each important function, I use this structure:

```text
Invariant
-> Where I checked
-> Protection / Check
-> Status
-> My reasoning
-> Consequence if broken
```

The objective is not only to generate a list of possible invariants. I verify each invariant against the actual execution path, separate protected behavior from suspicious behavior, and use a PoC when code-level evidence is required.

## Review Method

```text
Understand the architecture
-> Trace funds and data
-> Identify trust boundaries
-> Define invariants
-> Verify protections in code
-> Isolate suspicious behavior
-> Prove or reject it with a PoC
-> Write the finding clearly
```

## What I Track

| Area | Questions |
| --- | --- |
| Authentication | Who can trigger finalization? Is the messenger, endpoint, TSS, or counterpart verified? |
| Accounting | Does the deposited, escrowed, burned, minted, credited, or released amount remain consistent? |
| Token mapping | Does the local token map to the intended remote token? |
| Recipient | Is the intended recipient preserved through encoding, transport, and finalization? |
| Payload | Does decoded calldata exactly match what was encoded on the source chain? |
| Replay protection | Can the same message, transaction ID, or withdrawal be executed twice? |
| Failure handling | Where do funds go when message delivery or destination execution fails? |

## Current Level

I am building practical experience through local reviews, public contest scopes, simplified Foundry tests, and invariant-based analysis. These repositories are educational portfolio projects and independent security reviews, not official audits of production deployments.

## Contact

- GitHub: [Keedz1Off](https://github.com/Keedz1Off)
- Telegram: [@ETHkeedz1](https://t.me/ETHkeedz1)
- Email: [keedzyone@gmail.com](mailto:keedzyone@gmail.com)
