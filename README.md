
Previewing README.md
Azure Architecture Diagram Maker — distribution notes
Version 1.1.0

This folder is the shareable skill package. SKILL.md is the only runtime asset; references/host-notes.md holds optional host-specific delivery details. Nothing else is required.

Installing a shared copy
Import the azure-architecture-diagram-maker folder (or just SKILL.md) through the host's documented skill import/create mechanism. For instruction-only hosts, paste the body of SKILL.md; name it azure-architecture-diagram-maker with display title Azure Architecture Diagram Maker. Reload before first use. No fixed installation directory, extra files, or inherited environment variables are required.

First-use smoke check: ask for "Client -> App Service -> SQL Database; request flow only; use labelled boxes if icons are unavailable." Expect an SVG and, when rendering/viewing tools exist, an inspected PNG. Use synthetic data. Success on one host does not prove PNG capability on another.

Sharing this skill
Share only this folder's contents (SKILL.md, README.md, references/host-notes.md). Exclude helpers, node_modules, .git, caches, tokens, logs, customer examples, outputs, identities, machine paths, and private URLs. Retain the title, version, integration attribution (the optional renderer integration was inspired by Arturo Quiroga's Azure Architecture Diagram Builder; its repository, code and assets are not included or required), and the public icon-source guidance (https://learn.microsoft.com/en-us/azure/architecture/icons/). Nothing is automatically published.

What the skill does not do
Diagram-only. It does not run Well-Architected/WAF assessments, scoring, costing, hardening, deployment, IaC/Bicep/Terraform generation, manifests, or subscription/resource discovery. It requires no Git repository, cloned builder, account, API key, subscription, or custom MCP; an already-configured, approved renderer is optional.

Changelog
1.1.0 — Description rewritten with explicit trigger phrases and delegation to pptx / image-operations; added When NOT to Use, Quick start, Output format and Guardrails sections; moved installation/sharing notes to this README and host-specific delivery details to references/host-notes.md; spec-legal metadata block (category, icon, version). No diagram-fidelity, SVG-safety, rasterisation or acceptance-gate rules were removed.
1.0.0 — Initial single-file release.
