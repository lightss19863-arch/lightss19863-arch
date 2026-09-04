# Keshav Nagar
**Systems & Security Researcher · Founder, CrocodileSecurity**  
`Indore, MP, India` · [nyaya.cloud](https://nyaya.cloud) · `keshav@nyaya.cloud`

---

```
[Local-First Primitives]  ──►  [Applied Cryptography]  ──►  [Deterministic State Machines]
        Rust / Tauri v2              RFC 8785 / Ed25519            Fail-Closed Execution
```

I design and build deterministic, local-first desktop architectures and verify untrusted AI runtimes using applied cryptography and systems programming. My primary focus is engineering software where data confidentiality, auditability, and mathematical integrity are hard invariants, not afterthoughts.

---

### Core Engineering Focus

* **Deterministic Runtime Verification**: Engineering multi-stage content-addressed execution pipelines around untrusted LLM compilers. Rejection of ungrounded model outputs via deterministic assertion graphs, strict schema admission, and signed cryptographic receipts.
* **Local-First & Encrypted Storage**: Zero-cloud canonical architectures using SQLCipher AES-256 page-level encryption, OS credential store integration (Windows Credential Manager / macOS Keychain), and Argon2id-derived offline disaster recovery.
* **Transaction & Outbox Systems**: Monotonic state machines with row-revision compare-and-swap (CAS), RFC 8785 canonical digest validation, and append-only hash chains for crash-resilient desktop-to-cloud synchronization.
* **Application Security & Threat Modeling**: Security research covering authentication protocol validation, session boundary enforcement, zero-trust data egress gates, and prompt isolation against indirect prompt injection.

---

### Key Systems Architecture: Nyaya (Graphite) Workstation

Lead architect and developer of **[Nyaya](https://nyaya.cloud)**, an enterprise-grade, local-first legal workstation written in **Rust (Tauri v2)**, **TypeScript/Node.js**, and **React**.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        DESKTOP BOUNDARY (RUST)                         │
│                                                                        │
│   ┌──────────────────────┐               ┌─────────────────────────┐   │
│   │ Native Trust Bundle  │               │   SQLCipher Encrypted   │   │
│   │ (Ed25519 / P-256)    │               │   Workspace Database    │   │
│   └──────────┬───────────┘               └────────────┬────────────┘   │
│              │                                        │                │
│              ▼                                        ▼                │
│   ┌────────────────────────────────────────────────────────────┐       │
│   │ Run Outbox Service (Monotonic CAS & SHA-256 Event Chaining) │      │
│   └─────────────────────────────┬──────────────────────────────┘       │
└─────────────────────────────────┼──────────────────────────────────────┘
                                  │ Signed Egress (RFC 8785 JCS)
                                  ▼
┌────────────────────────────────────────────────────────────────────────┐
│                  CLOUD RUNTIME (PROPOSAL-ONLY COMPILER)                │
│                                                                        │
│   [validate_bindings] ──► [generate_proposal] ──► [deterministic_safety]
│                                                          │             │
│   [final_validation]  ◄── [sign_receipts]    ◄───────────┘             │
│                                                                        │
│   * Zero Canonical Mutation           * Expiring Distributed Leases    │
│   * Hierarchical Receipt Tree         * Data-Only Quarantined Prompts  │
└────────────────────────────────────────────────────────────────────────┘
```

#### Technical Guarantees Implemented:
1. **Proposal-Only Cloud Execution**: The cloud runtime possesses zero canonical write authority. It emits staged proposals with `proposalOnly: true` and `noCanonicalMutation: true`. Promotion requires a native 4-eyes approval transaction verified in Rust.
2. **Assertion Support Graph**: Generated substantive clauses must link to authenticated source spans or verified authorities. Unsupported propositions fail closed into explicit `unresolved:<clauseId>` issues.
3. **Receipt Hierarchy**: Section-level component receipts close into ordered subject digests, which close into terminal execution receipts signed via Ed25519 over RFC 8785 canonical JSON.
4. **Cross-Runtime Encoding Precision**: String redlining and diff boundaries are tracked strictly in Unicode code points, eliminating encoding drift and AST coordinate desynchronization across Rust, Node.js, and browser DOMs.

---

### Technical Primitives & Tooling

```
Systems & Desktop       Rust, Tauri v2, SQLCipher (AES-256), Win32 / macOS Keychain APIs
Languages               Rust, TypeScript, JavaScript (ES6+), Python, SQL
Storage & Distributed   PostgreSQL (Advisory / Distributed Leases, CAS), SQLite FTS5
Security & Cryptography RFC 8785 JCS, Ed25519, P-256 ECDSA, Argon2id, AES-256-GCM, SHA-256
Frontend Runtime        React, Vite, Web Components, Custom Virtualized Editors
DevOps & Infrastructure Linux, Bash, PowerShell, Git, CI/CD Hardening, Docker
```

---

### Contact & Verification
* **Engineering & Platform:** [nyaya.cloud](https://nyaya.cloud)
* **Security Assessments:** CrocodileSecurity (`keshav@nyaya.cloud`)
* **LinkedIn:** [keshav-nagar](https://www.linkedin.com/in/keshav-nagar-1709372a9)

<!--
**lightss19863-arch/lightss19863-arch** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
