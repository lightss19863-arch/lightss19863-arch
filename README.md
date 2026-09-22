# Hey, I'm Keshav 👋

I'm building [Nyaya](https://nyaya.cloud) — a local-first desktop workstation for Indian lawyers and advocates. Think of it as legal case management that actually respects client confidentiality: everything is encrypted on your machine, the cloud only sees what you explicitly push, and even then it can't modify your canonical records.

Written in **Rust** (Tauri v2) on the backend and **React** on the frontend. The database is SQLite encrypted with SQLCipher, and encryption keys live in Windows Credential Manager / macOS Keychain — they never touch the filesystem. I'm unreasonably proud of how the disaster recovery system works (Argon2id key derivation, AES-256-GCM envelope, crash-safe atomic writes), and unreasonably tired of debugging cross-runtime Unicode encoding issues between Rust, Node.js, and the browser DOM.

Currently piloting with a few advocates at the **Madhya Pradesh High Court** (Indore Bench).

### Open source stuff I extracted from this project

- [`jcs-canonical-json`](https://github.com/lightss19863-arch/jcs-canonical-json) — RFC 8785 deterministic JSON serialization. Built this after an annoying afternoon figuring out why my receipt signatures were breaking on emoji keys (UTF-16 sort order ≠ UTF-8 byte order, who knew).
- [`os-keyvault`](https://github.com/lightss19863-arch/os-keyvault) — Cross-platform OS credential store wrapper. Because writing encryption keys to a config file next to the database is security theater.
- [`native-trust-verify`](https://github.com/lightss19863-arch/native-trust-verify) — Ed25519 / P-256 signature verification against compiled-in JWK trust bundles. The desktop uses this to verify cloud-generated documents before accepting them.

### What I work with daily

Rust · Tauri v2 · React · TypeScript · SQLCipher · SQLite · PostgreSQL · Ed25519 · AES-256-GCM · Argon2id

### Reach me

- **Email:** keshav@nyaya.cloud
- **LinkedIn:** [keshav-nagar](https://www.linkedin.com/in/keshav-nagar-1709372a9)
- **Product:** [nyaya.cloud](https://nyaya.cloud)
