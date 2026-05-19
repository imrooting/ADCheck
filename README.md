# AD Pentest Validator

**A browser-based Active Directory penetration testing reference tool for authorized security assessments.**

Live at: `https://imrooting.github.io/ADCheck/index.html`

---

## What is this?

AD Pentest Validator is a single-file, zero-dependency HTML tool that guides security professionals through Active Directory penetration testing engagements. It replaces scattered notes and cheat sheets with a structured, interactive workflow — from initial enumeration through attack chain selection to post-exploitation.

Built for **authorized red team engagements and penetration tests only.**

---

## Features

### Guided Wizard
Step-by-step workflow that adapts to your environment. Answer questions about what you found during enumeration and the tool reveals only the attack paths that are actually applicable — no information overload.

### Dual-Environment Commands
Every attack card shows separate command tabs for:
- **🐉 Kali / Linux** — Impacket, NetExec, Certipy, pywhisker, bloodyAD, krbrelayx, and more
- **🪟 Windows** — Rubeus, Whisker, Certify, PowerView, PowerMad, SharpSCCM, PowerUpSQL, and more

### Attack Status Tracking
Mark each attack path as you work through it:
- 🔴 **Confirmed Vuln** — environment is affected
- ✅ **Exploited** — successfully executed
- ⬜ **Not Vulnerable** — tested, not applicable
- 🔍 **Investigate Later** — flagged for follow-up

### Smart Sidebar
The left sidebar updates dynamically as you work:
- **Enumeration Findings** — shows everything you selected in Step 3
- **Attack Paths** — grouped by status (Confirmed Vuln → Exploited → Investigate Later → Not Vulnerable → Untagged), click any entry to jump directly to that attack card

### Completion Checklist
110+ item checklist covering all major attack categories with a progress bar — useful for ensuring full coverage before wrapping an engagement.

### Quick Links
Copy-ready one-liner commands grouped by attack category for fast reference without going through the wizard.

### Cheatsheet
Key command sequences for Relay, Coercion, ADCS, mitm6, Post-Exploitation, and Kerberoasting — all in one scrollable view.

---

## Attack Coverage

| Category | Attacks |
|---|---|
| **SMB Relay** | SMB→SMB SAM dump, SMB→LDAPS DA creation, SOCKS proxy relay |
| **IPv6 / mitm6** | RBCD via mitm6, DA creation via mitm6 |
| **WebDAV / WebClient** | HTTP→LDAP relay, RBCD chain, Shadow Credentials |
| **Authentication Coercion** | PrinterBug (MS-RPRN), PetitPotam, DFSCoerce, ShadowCoerce, Coercer |
| **ADCS** | ESC1, ESC4, ESC8, full Certipy/Certify workflow |
| **Delegation** | Unconstrained + coercion → DCSync, Constrained S4U2Proxy, RBCD |
| **DACL / ACL Abuse** | GenericAll/GenericWrite, WriteDACL→DCSync, WriteOwner, dacledit, owneredit |
| **Shadow Credentials** | pywhisker, Whisker, certipy shadow, PKINIT chain |
| **Credential Attacks** | Kerberoasting, targetedKerberoast, AS-REP roasting, NTLMv1→crack.sh |
| **LAPS** | pyLAPS, LAPSToolkit, PowerView, SharpLAPS |
| **SCCM** | NAA extraction, client push attack, SCCMHunter, SharpSCCM |
| **WSUS** | HTTP fake update via SharpWSUS |
| **MSSQL** | xp_cmdshell, linked server abuse, PowerUpSQL, SQLRecon |
| **Post-Exploitation** | DCSync, Pass-the-Hash, Pass-the-Ticket, Golden Ticket, persistence |

---

## Tools Referenced

### Linux / Kali
`impacket` · `netexec (nxc)` · `certipy` · `bloodhound-python` · `responder` · `mitm6` · `coercer` · `pywhisker` · `PKINITtools` · `bloodyAD` · `dacledit` · `owneredit` · `targetedKerberoast` · `pyLAPS` · `LAPSToolkit` · `krbrelayx` · `sccmhunter` · `rbcd.py` · `PetitPotam` · `printerbug` · `hashcat`

### Windows
`Rubeus` · `Whisker` · `Certify` · `PowerView` · `SharpView` · `PowerMad` · `Inveigh` · `mimikatz` · `SharpSCCM` · `SharpWSUS` · `SharpLAPS` · `PowerUpSQL` · `SQLRecon` · `SpoolSample` · `SharpSpoolTrigger` · `PSPKIAudit`

---

## Usage

The tool runs entirely in the browser with no backend, no tracking, no external calls (except Google Fonts for typography). It works offline once loaded.

**Recommended workflow for an engagement:**

1. Open the tool at the start of your internal network assessment
2. Work through **Step 1** (do you have credentials?) and **Step 2** (run enumeration)
3. In **Step 3**, check off everything you confirmed during enumeration
4. Select the attack paths you want to pursue from the revealed list
5. Click **Show Full Attack Details** — your personalized attack runbook is generated
6. Use the **Kali / Windows tabs** on each card depending on your attack platform
7. Mark each attack with a status as you test it — the sidebar tracks your progress
8. Use the **Checklist** view to verify full coverage before wrapping up

---

## Version History

| Version | Changes |
|---|---|
| v5.0 | White theme, dual Kali/Windows command tabs, smart status-grouped sidebar, 4-status tracking system, expanded tool coverage |
| v4.0 | Dark theme, guided wizard, attack chain builder, quick links, checklist |

---

## Contributing

Pull requests welcome. If you have additional attack chains, tool alternatives, or enumeration steps to add, open an issue or PR.

---

## License

MIT License — free to use, modify, and distribute. Attribution appreciated but not required.
