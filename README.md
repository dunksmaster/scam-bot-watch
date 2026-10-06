# Scam Bot Watch

A public list of fake crypto trading-bot repos and fake or cracked software lures on GitHub that steal keys or run hidden malware.

## Support this work

If this list helped you, tips are welcome over Lightning:

**Lightning address:** `btckane@cake.cash`

It's reusable, so you can send any amount. There are no one-time invoices.

![Lightning tip QR code for btckane@cake.cash](assets/lightning-tip-qr.jpg)

## What this is

This is a public list of scam repositories on GitHub. It covers fake crypto trading bots (Polymarket, Hyperliquid, Solana sniper, pump.fun, MEV and copy-trade bots) and fake or cracked software lures ("free" paid tools with a crack, activator or keygen). They steal private keys or run hidden malware. Every repo is checked read-only, and each entry shows whether it has been reported to GitHub.

## How to spot a fake bot

- It asks for your private key or seed phrase.
- It tells you to download a zip or exe, or to "run setup.exe".
- It tells you to turn off your antivirus or click "run anyway".
- The code has hex or base64 strings that hide what they are, or connects to hidden servers.
- The code downloads something and runs it.
- The repo includes big .pkg or .zip archives.
- It suddenly gets lots of stars from new accounts.
- It promises guaranteed profit.

**Never run a trading bot with a wallet that holds real funds. Never paste your private key or seed phrase anywhere.**

## Findings

Repo names are plain text, not links, so this page doesn't send traffic to malware.

| Date | Repo | Verdict | Evidence | Reported to GitHub |
|---|---|---|---|---|
| 2026-09-27 | gulelmatthews/Polymarket-Perpetual-Bot | Confirmed malware | Hidden server api.failproxy.space (obfuscated); downloads and runs a Windows payload in memory; asks for private keys; fake stars | Yes |
| 2026-09-27 | ArtemPavlov1994/polymarket-prediction-bot | Confirmed malware | Same loader as above (byte-identical files); reversed-hex endpoint to api.failproxy.space in support/site.py; in-memory PE loader in support/plugin.py; 14 MB bundled archive | Yes |

## Known scam patterns

Each pattern has a scam card in [scam-cards/](scam-cards/) with the evidence, red flags, and what to do if you already ran it. Repo names are plain text, not links.

- **Fake "free/cracked" paid security software:** BarricadeHerbalist/Acunetix-Scanner-2026. It promises a cracked Acunetix 2026 with an activator and keygen. It contains no real code, sends you to a hidden-JavaScript GitHub Pages "download" page, and has an empty release with an archive password (`2026`). Verdict: likely scam. Not yet reported to GitHub. [Card](scam-cards/BarricadeHerbalist-Acunetix-Scanner-2026.md)

## How findings are checked

- Source files are read only through the GitHub API.
- Nothing from a suspect repo is run, cloned or downloaded.
- A repo is marked "Confirmed malware" only when its code proves it.

## Disclaimer

This list is provided as-is, for information only, and may be incomplete. A repo that isn't listed here isn't necessarily safe. Always check code yourself before you run it, and never trust a trading bot with real funds.
