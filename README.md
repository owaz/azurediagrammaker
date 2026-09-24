# Azure Architecture Diagram Maker

A reusable skill for creating clear Azure architecture diagrams as editable SVG and PNG assets.

## Overview

This project contains the `SKILL.md` instruction set for an Azure architecture diagram generator. It is designed to help an agent or host produce:

- Azure architecture diagrams from prompts or supplied artifacts
- Diagram cleanup and refinement for existing Azure visuals
- Editable, self-contained SVG output
- Optional PNG previews when the host supports rendering or viewing

The focus is on:
- accurate Azure topology
- clean layout and readable flow
- faithful traffic direction and boundaries
- editable vector output suitable for documentation and review

## What this skill does not do

This skill is strictly diagram-focused. It does not provide:

- Well-Architected / WAF assessments
- scoring or benchmarking
- cost estimation
- hardening guidance
- deployment planning
- IaC generation
- manifests or resource discovery

If a detail is missing or ambiguous, it asks for the required information instead of inventing topology.

## Included files

- `SKILL.md` — the reusable instruction set
- `README.md` — project overview and usage notes

## How to use the skill

### 1) Import the skill

Import `SKILL.md` into your host’s skill or instruction system.

Suggested name:
- `azure-architecture-diagram-maker`

Suggested display title:
- `Azure Architecture Diagram Maker`

### 2) Describe the architecture

Use a prompt that clearly states the Azure resources, flow direction, and any required layout constraints.

Example prompts:
- "Create an Azure architecture diagram for a web application with App Service, SQL Database, and Azure Front Door."
- "Refine this diagram to match the topology: Client -> API Management -> Function App -> Cosmos DB, with WAF in front of the public endpoint."
- "Generate an SVG for this Azure VNet design with subnets, firewall, and private endpoints."
- "Create a PNG preview of this architecture and keep it readable at full scale."

### 3) Choose output format

By default, the skill prefers:
- editable SVG
- PNG preview when supported by the environment

You can also request:
- SVG only
- PNG only
- SVG plus PNG

## Quick start

1. Open your agent or skill-enabled environment.
2. Import `SKILL.md`.
3. Provide a prompt describing the Azure architecture.
4. Review the generated SVG.
5. Request a PNG preview if the host supports rasterization.
6. Refine the diagram with more topology detail if needed.

## Diagram quality standards

The skill is designed to produce diagrams that are:

- readable and logically structured
- faithful to the described Azure topology
- suitable for technical documentation and review
- editable in SVG format
- self-contained without external assets

It applies best practices such as:
- clear left-to-right primary flow
- separate lanes for different traffic classes when needed
- explicit labels and return-path handling
- valid connector routing
- readable legends and consistent styling
- safe SVG construction without scripts or external dependencies

## Output expectations

When used in a compatible environment, the expected output is:

- an SVG diagram
- a PNG preview if rasterization is available
- a final response that includes the output artifact link or attachment
- any necessary assumptions or limitations clearly stated

## Repository purpose

This repository stores the reusable skill definition and documentation for Azure diagram generation workflows. The skill is intended to be imported into a host environment and used without requiring a repository clone, custom server, or Azure sign-in.

## Example use cases

- Draw an Azure App Service + SQL architecture
- Show API Management routing to backend services
- Model Azure Front Door + WAF + App Service patterns
- Create an Azure VNet diagram with subnets, route tables, and private endpoints
- Refine an existing architecture sketch into a cleaner, review-ready diagram

## Notes

This project is intentionally focused on diagram creation rather than architecture evaluation. It is best used when the goal is to generate or improve clear Azure system visuals for communication, documentation, and review.
