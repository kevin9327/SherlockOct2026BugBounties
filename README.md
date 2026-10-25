# Sherlock Live Bug Bounties — October 2026 Newly Updated Targets (`$4,500,000 USDC` Combined Cash Pool)

![Sherlock October 2026 Bug Bounties Banner](banner.png)

- **Official Portal:** https://audits.sherlock.xyz/bug-bounties
- **Combined Active Cash Pool:** **`$4,500,000 USDC`**
  1. **Aero (`$500,000 USDC`, Updated October 21, 2026)**
  2. **Kamino (`$1,000,000 USDC`, Updated October 16, 2026)**
  3. **Babylon (`$500,000 USDC`, Updated October 2, 2026)**
  4. **Aave V4 (`$2,500,000 USDC`, Updated September 29, 2026)**
- **Verification SHA-256:** `e05bbfde6e98008101cfdb0e2102a62334c137a1795dbfc336c4980a9b0f2568`

---

## 1. Protocol Invariant Harnesses (`verify_sherlock_bounties.py`)

1. **Aero (`$500,000 USDC`):** Detects stranded sub-rate wei (`rewardAmount % EPOCH_DURATION`) across multi-epoch `notifyRewardAmount` calls in Ve(3,3) gauges and verifies `1e36`-scaled `rewardPerToken` rollover conservation.
2. **Kamino (`$1,000,000 USDC`):** Verifies Solana kToken CLMM elevation-group liquidation seizure capping when `debt * (1 + liquidationBonusBps) > totalCollateral` near the 95% LTV boundary.
3. **Babylon (`$500,000 USDC`):** Verifies Schnorr Extractable One-Time Signature (EOTS) private key recovery $x = (s_1 - s_2)(e_1 - e_2)^{-1} \bmod q$ upon finality provider double-signing at the same Bitcoin block height.
4. **Aave V4 (`$2,500,000 USDC`):** Verifies Hub-and-Spoke deficit elimination ray-math ($10^{27}$) conservation across spoke bad-debt socialization.

---

## 2. Reproducible Verification (`exit code 0`)

```bash
python SherlockOct2026BugBounties/verify_sherlock_bounties.py
```
