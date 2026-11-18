# LienWaiverSeal

**Local-first lien waiver, release, and payment evidence sealer for field operators and GCs.**

Offline. Deterministic. Pay once. Compatible with QuantumGuard CONTRACT-v1, ProgressPaymentSeal, InvoiceSeal, and the Operator Pages suite.

## Why LienWaiverSeal?

Lien waivers are critical for payment but easy to dispute later: was the waiver conditional or unconditional? Through what date? For what amount? Signed by whom?

LienWaiverSeal captures a structured lien waiver (type, amount, parties, through-date, exceptions, supporting progress payment hash) and seals it into a client-verifiable QuantumGuard evidence bundle.

- No SaaS. No subscription. Runs completely offline after key setup.
- Owners, GCs, or lenders verify the pack with the free QuantumGuard verifier (`qg verify`).
- Pairs with ProgressPaymentSeal for the pay application it releases against, InvoiceSeal for final billing, and MediaSeal for any attached scans.
- Deterministic: same inputs → same sealed pack.

## Quick Start

```bash
# Recommended for real Ed25519 signatures
pip install cryptography

python3 src/lienwaiverseal.py --demo
python3 src/lienwaiverseal.py --json samples/lien-waiver-001.json --out sealed-lien-waiver.json
```

Verify the output with the QuantumGuard CLI (from the quantumguard repo):

```bash
qg verify sealed-lien-waiver.json
```

Expected verdict: **PASS**.

## What you can sell

| SKU       | Price | Includes                                      |
|-----------|-------|-----------------------------------------------|
| Operator  | $79   | CLI + sample templates + key setup guide + 1-year email support |
| Command   | $199  | + batch mode + HTML logger + reseller rights for client packs |
| Agency    | $499  | + white-label + multi-site key management + design partner onboarding |

Purchase / access: danpennic@gmail.com  
Or use the Operator Pages Stripe checkout flow (create a dedicated Payment Link).

Source remains free under Apache-2.0 OR MIT. Commercial Operator Pack sold separately.

## Stack Fit

- Python CLI (same family as ProgressPaymentSeal, InvoiceSeal, SubmittalSeal)
- Emits QuantumGuard CONTRACT-v1 bundles (Ed25519, deterministic canonical JSON)
- Local key storage (PEM)
- Designed to drop into the Operator Pages field stack

## License

Apache-2.0 OR MIT
