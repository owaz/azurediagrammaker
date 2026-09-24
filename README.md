# Azure Architecture Diagram Maker

A reusable skill for creating clear Azure architecture diagrams as editable SVG and PNG assets.

## What this skill does

This repository contains the `SKILL.md` instruction set for an Azure architecture diagram generator. It is designed to help an agent or host produce:

- Azure architecture diagrams from natural-language prompts or supplied artifacts
- Diagram cleanup and refinement for existing architecture visuals
- Editable, self-contained SVG output
- Optional PNG previews when the host supports rendering and viewing

The skill focuses on diagram fidelity, readable layout, and accurate flow direction. It does not provide architecture assessments, pricing guidance, security hardening recommendations, or infrastructure deployment instructions.

## Included files

- `SKILL.md` — the reusable skill instructions
- `README.md` — project overview and usage guidance

## How to use the skill

### 1) Import the skill into your environment

Import `SKILL.md` using your host's skill or instruction system.

Suggested name:

- `azure-architecture-diagram-maker`

Suggested display title:

- `Azure Architecture Diagram Maker`

### 2) Describe the architecture you want

Use a prompt that clearly outlines the Azure resources and traffic relationships.

Examples:

- "Create an Azure architecture diagram for a web application with App Service, SQL Database, and Azure Front Door. Use left-to-right flow and include return traffic."
- "Refine this topology into a clean diagram: Client -> API Management -> Function App -> Cosmos DB, with WAF in front of the public endpoint."
- "Generate an SVG for this Azure VNet design with subnets, firewall, and private endpoints."
- "Create a PNG preview of this architecture and keep the layout readable at full scale."

### 3) Choose the output format

By default, the skill prefers:

- editable SVG
- PNG preview when a compatible renderer is available

You can also request one of these explicitly:

- SVG only
- PNG only
- SVG plus PNG

## Scope and guardrails

This skill is focused on diagram generation, not architecture review.

It intentionally avoids:

- Well-Architected assessments
- WAF/BAF scoring
- cost estimation
- security hardening recommendations
- deployment planning
- infrastructure-as-code generation
- subscription or resource discovery

If a detail is ambiguous or missing, the skill asks only for the missing material information instead of inventing resource relationships.

## Diagram quality standards

The skill is designed to produce diagrams that are:

- readable and logically structured
- faithful to the described Azure topology
- suitable for technical documentation and review
- editable in SVG format
- self-contained without external assets

It emphasizes:

- clear primary traffic flow from left to right
- separate lanes for different traffic classes when needed
- accurate labels and return-path handling
- valid endpoint-to-endpoint connections
- minimal, readable legends
- safe SVG construction without scripts or external dependencies

## Output expectations

When used in a compatible environment, the expected result is:

- an SVG diagram
- a PNG preview if the host supports rasterization
- a final response containing the artifact link or attachment
- any assumptions or limitations clearly noted

## Repository purpose

This repository stores the reusable skill definition and documentation for Azure diagram generation workflows. The skill is intended to be imported into a host environment and used without requiring a repo clone, custom server, or Azure sign-in.

## Quick start

1. Open your agent or skill-based environment.
2. Import `SKILL.md`.
3. Run the skill with an Azure architecture request.
4. Review the produced SVG and optional PNG.
5. Refine the request if more detail is needed.

## Example use cases

- Draw an Azure App Service + SQL architecture
- Show API Management routing to backend services
- Model Azure Front Door + WAF + App Service patterns
- Create an Azure VNet diagram with subnets, route tables, and private endpoints
- Refine an existing architecture sketch into a cleaner, review-ready diagram

## Notes

This project is intentionally focused on diagram creation rather than architecture evaluation. It is best used when the goal is to generate or improve clear Azure system visuals for communication, documentation, and review.
