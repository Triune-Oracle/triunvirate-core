# Hash Anchoring Specification

## Purpose
Hash anchoring is used to provide tamper-evidence for the Triumvirate's system logs and state transitions. It ensures that the "Memory Core" remains immutable and verifiable.

## Mechanism
1. **Hash Generation**: A SHA-256 hash is generated for critical log files (e.g., `swarm_scan.json`) at the end of each execution cycle or daily.
2. **Anchoring**: The generated hash is submitted as a transaction to a public blockchain.
3. **Verification**: External auditors can re-hash the local logs and compare them against the on-chain anchor to verify integrity.

## Scope
- `swarm_scan.md` / `swarm_scan.json`
- Execution summaries
- QA reports
- Phase transition manifests

## Constraints
- **No Execution Logic**: No system logic or smart contracts are triggered by the anchoring process.
- **Proof Only**: The anchor serves as a timestamped proof of existence and integrity.

## Target Networks
- **Primary**: Ethereum Mainnet
- **Fallback**: Polygon (for cost-efficiency during high-frequency cycles)
