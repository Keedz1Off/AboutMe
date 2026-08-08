# About Me

I am a junior smart contract security researcher looking for real-world experience in Web3 security.

My main focus is bridge security, cross-chain message flows, and L1/L2 architecture. I trace complete protocol flows, define security invariants, verify their protections in code, and prepare PoC ideas for suspicious behavior.

## Current Contest Review

### Push Chain Gateway

I am conducting an independent, contest-oriented review of the Push Chain EVM Gateway scope.

The review covers:

```text
UniversalGateway source flow
transaction type detection and routing
native and ERC20 deposits
rate limits and protocol fees
UniversalTx event integrity
off-chain TSS trust boundary
Vault finalization
CEA deployment and execution
revert and refund flow
```

For each important function, I record:

```text
Invariant
-> Where I checked
-> Protection / Check
-> Status
-> My reasoning
```

This is the most complete end-to-end verification exercise currently included in my portfolio.

## Primary Security Reviews

### Arbitrum

Deposit and withdrawal flows, escrow, retryable tickets, address aliasing, gateway authentication, token mapping, mint/release accounting, and simplified Foundry PoC practice.

### Optimism

Standard Bridge deposit and withdrawal flows, messenger authentication, counterpart verification, token accounting, burn/mint logic, and finalization.

### LayerZero OFT

Send and receive flows, debit/credit accounting, payload encoding, enforced options, endpoint delivery, trusted peers, compose execution, and exploit-lab practice.

## Supporting Architecture Studies

### Arbitrum L3

An additional architecture study of L2-to-L3 bridge flows, retryable tickets, and L3-specific trust assumptions.

### Sky / DAI Bridge Fork

An additional study of an Optimism-based bridge fork, including escrow, token registration, withdrawal limits, and governance-controlled functions.

These repositories support the main portfolio by showing how bridge assumptions change across forks and layered architectures.

## Break Think

The most important part of my portfolio is the Break Think files.

In these files, I practice identifying invariants and analyzing what may happen if they break. I then verify each invariant against the relevant functions instead of treating AI-generated invariant lists as findings.

## Review Method

```text
Understand the architecture
-> Trace funds and data
-> Define invariants
-> Verify protections in code
-> Isolate suspicious behavior
-> Prove or reject it with a PoC
```

Portfolio repositories: https://github.com/Keedz1Off
