## Santosh Kumar Puppala

AI/ML Platform Architect. I work on **authorization flaws in open-source software** — the class of bug where
a system correctly authenticates who you are and then fails to check what you are allowed to do.

Most of my public work is vulnerability research done under coordinated disclosure: I read source, reproduce
the issue locally, report it privately to the maintainers, and stay with it until a fix ships.

### Security research

- Vulnerabilities reported under coordinated disclosure across open-source projects; the public, fixed and credited ones are listed below
- **CVE identifiers assigned** for a number of these; several credited to me by name
- Most of the work concentrates on one root-cause class: **broken access control** — IDOR, missing
  authorization checks, and read/write permission asymmetries
- Some affected projects are used in public-sector and civic settings

I also write up the methodology, because a single fixed bug helps one project and a documented detection
pattern helps everyone maintaining similar code.

### Fixes, not just reports

Where a maintainer prefers it, I write the patch myself:

- **[chirpstack/chirpstack#982](https://github.com/chirpstack/chirpstack/pull/982)** — *Require gateway-admin
  for relay-gateway update/delete.* Two write operations were guarded by the permission check meant for
  listing, so any tenant member — including a read-only API key — could modify or delete gateway
  configuration. Merged into `master`.

### Published advisories

A sample of findings that are public, fixed, and credited:

| Advisory | Project | Issue | Fixed in |
|---|---|---|---|
| [GHSA-7cqp-qvh5-7x85](https://github.com/openfoodfoundation/openfoodnetwork/security/advisories/GHSA-7cqp-qvh5-7x85) | Open Food Network | An enterprise manager could read and alter customer account balances belonging to a different enterprise | 5.7.4 |
| [GHSA-9vjj-v46c-c5qf](https://github.com/gammu/gammu/security/advisories/GHSA-9vjj-v46c-c5qf) | Gammu | A crafted SMS sender ID could inject shell metacharacters into a command the SMS daemon runs | 1.43.3 |
| [GHSA-vf9q-phg3-hqj6](https://github.com/OpenFn/lightning/security/advisories/GHSA-vf9q-phg3-hqj6) | OpenFn Lightning | An authenticated user could read and modify data in projects they were not a member of by supplying that project's identifier | 2.17.0 |
| [CVE-2026-54732](https://github.com/elwerene/libreoffice-convert/security/advisories/GHSA-gmxc-r82q-347r) | libreoffice-convert | An unsanitized filename allowed writing outside the intended directory | 1.8.2 |
| [CVE-2026-16454](https://github.com/eclipse-hawkbit/hawkbit/security/advisories/GHSA-92r3-p8c2-3fpx) | Eclipse hawkBit | A `Range` header skipped the download authorization check, letting one device fetch another's firmware | 1.0.4 |
| [CVE-2026-55610](https://github.com/InvoiceShelf/InvoiceShelf/security/advisories/GHSA-vgx6-6cqr-m8qr) | InvoiceShelf | User records were looked up by global id without checking company ownership | 2.4.1 |

### Writing

- [A walk-through of a high-severity cross-company account-takeover bug in a widely-used open-source invoicing app (CVE-2026-55610)](https://medium.com/@santhoshkumar7794/a-walk-through-of-a-high-severity-cross-company-account-takeover-bug-in-a-widely-used-open-source-e7596a411268)
- [Finding real bugs: a repeatable methodology for open-source vulnerability research](https://medium.com/@santhoshkumar7794/finding-real-bugs-a-repeatable-methodology-for-open-source-vulnerability-research-eacba5311acf)

More on [Medium](https://medium.com/@santhoshkumar7794).

### Elsewhere

- LinkedIn: https://www.linkedin.com/in/santoshpuppala/

*Reporting a vulnerability in something I maintain? Open a private security advisory on the repo.*
