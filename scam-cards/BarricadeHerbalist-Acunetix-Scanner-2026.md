# Scam card: BarricadeHerbalist/Acunetix-Scanner-2026

## Summary

A fake "free cracked Acunetix 2026" repo that has no real software in it. It sends you to a hidden-code download page and a password-protected archive, which is the classic way malware gets delivered.

## Repo

- **URL (plain text, don't visit):** `github.com/BarricadeHerbalist/Acunetix-Scanner-2026`
- **Account:** `BarricadeHerbalist`. Created 2026-08-23 06:02 (Budapest time). 0 followers, 0 following, 1 public repo (this one).
- **Repo created:** 2026-10-02 04:58 (Budapest time)
- **Stars:** 14. Forks: 0. Watchers: 0.
- **Last push:** 2026-10-06 10:30 (Budapest time). This was an automated "keep-alive" commit (see below).
- **Download page it points to (defanged, don't visit):** `hxxps://barricadeherbalist[.]github[.]io/Acunetix-Scanner-2026/`
- **Checked:** 2026-10-06 around 11:55 (Budapest time), read-only through the GitHub API

## Verdict

**Likely scam / malware lure (high confidence). Not "confirmed malware".**

The repo contains no Acunetix software and no working code. Everything in it exists to push you to a download page whose code is deliberately hidden, and then to a password-protected archive. The actual payload isn't stored in the repo, and we didn't decode or run the hidden page code, so we can't prove from readable code what the download does. That's why this is "likely" and not "confirmed".

## The lure

Acunetix is an expensive commercial web security scanner. This repo promises a free "premium/pro" copy plus an "activator, patch, serial, activation key, license key, trial reset and license generator" (repo description; README.md lines 3, 16–18). In other words, it's offering cracked paid software. People looking for a free copy of a pricey security tool are the target.

## How the scam works (what we actually saw)

1. **Big download button to an outside page.** README.md line 9: "DOWNLOAD LATEST RELEASE" links to the repo's GitHub Pages site (`hxxps://barricadeherbalist[.]github[.]io/Acunetix-Scanner-2026/`). That's not a normal GitHub download.
2. **The download page's code is hidden.** index.html line 1 is the whole page: one line of about 72 KB of scrambled JavaScript (`<script>;Function("…")()`). It unscrambles itself with a custom character-swap routine and then runs the hidden result as new code (`(()=>{}).constructor(…)`). The page has no visible text or links at all. Real download pages don't hide what they do like this.
3. **An empty "release" with a password.** README.md line 22 links to a release (tag `818f9556`, published 2026-10-02 05:01 Budapest time). The release has **zero files attached**. Its notes only repeat the link to the outside page and say **"PASSWORD: `2026`"**.
4. **"Unpack the archive, open README.txt."** README.md lines 25–27 tell you to unpack a downloaded archive and follow the instructions in a README.txt inside it. That README.txt isn't in this repo.
5. **Fake "source code".** src/src.cpp (lines 1–4113) is the same 9-line "hello world" program (it prints "Sum: 15") copied 457 times. It's only there so GitHub labels the repo as C++ and it looks like a real project. README.md line 45 then tells contributors to "Use Python", which doesn't fit.
6. **Fake popularity.** README.md line 5 shows a hard-coded "downloads 16.6k" badge. It's a static image, not a real counter. Line 7 claims an Apache-2.0 license, but the repo has no license file.
7. **A robot that fakes activity.** .github/workflows/ferret.yml (lines 3–4, 14–18) runs every 2 hours. Each run adds a timestamp to `.github/ferret` and commits it with the message "Initial commit". 19 of the repo's 25 commits are these robot commits, so the repo always looks "recently updated" in search.
8. **Auto-publishing the download page.** .github/workflows/pages.yml (lines 1–30) publishes index.html as the GitHub Pages site.

## Why it's dangerous

**What we saw:**
- The real "download" happens off GitHub, through a page whose code is deliberately hidden (index.html line 1).
- The file you'd end up with is a password-protected archive (release notes say "PASSWORD: 2026"; README.md lines 25–27). Antivirus and GitHub's own scanning usually can't look inside a password-protected archive.
- There's no real software here at all (src/src.cpp is filler).

**Typical of this lure pattern (not proven for this repo):**
- In this kind of campaign, the hidden page usually sends you to a file-hosting site with an archive that contains an **information stealer**. That's malware that grabs saved browser passwords, cookies and logged-in sessions, crypto wallets, Discord/Telegram sessions, and SSH/API keys, then uploads them to the attacker.
- The README.txt inside the archive often tells you to turn off your antivirus or add an exception "because cracks get flagged". We didn't see that text in this repo because it would sit inside the archive.
- Some variants also install remote-access tools or crypto miners.

## Red flags to spot

- It offers paid software for free, with "crack", "activator", "keygen", "patch", "license generator" or "trial reset".
- The download button goes to a GitHub Pages site (`*.github[.]io`) or another outside site, not a real file in the repo.
- A release with no files, or only a link and a password.
- "The password is 2026" (or any archive password).
- The source code is obviously filler (the same few lines repeated over and over).
- Badges claiming thousands of downloads on a repo that's only a few days old.
- A brand-new account with one repo, no followers, and stars that appeared all at once.
- Many commits all called "Initial commit", made automatically on a timer.

## How to avoid it

- Get security tools only from the vendor's official website, or use well-known free and open-source alternatives.
- Never download "cracked" or "activated" software. Cracks are one of the most common ways malware spreads.
- Don't open password-protected archives from strangers, and never turn off your antivirus because a download tells you to.
- Don't trust stars or download badges. They're easy to fake.

## If you already ran it

1. **Disconnect** the computer from the internet (unplug the cable or turn off Wi-Fi).
2. From a **different, clean device**, **change your passwords**, starting with email, banking, GitHub, cloud and work accounts. Turn on two-factor authentication wherever you can.
3. **Rotate API keys, access tokens and SSH keys** that were on that computer (GitHub, cloud providers, CI/CD, password managers, etc.).
4. **Revoke browser sessions and tokens.** Log out of all sessions in Google, Microsoft, GitHub, Discord, Telegram and so on, because stolen cookies can get around passwords.
5. If you have crypto, **move it to a brand-new wallet created on a clean device**. Treat any wallet or seed phrase that was on the infected computer as compromised.
6. **Scan, then reinstall the operating system.** Malware like this can hide well, so a clean reinstall is the safest fix.
7. **Report the repo to GitHub** at github.com/contact/report-abuse.

## Reported to GitHub

Not yet
