# CAD Engineering Agent Workflow

AI Engineering Workflow focused on refrigeration equipment, CAD automation, long-context reasoning, and sheet metal manufacturing analysis.

---

## Overview

CAD Engineering Agent Workflow is a long-running multi-agent system designed for mechanical engineering and refrigeration equipment development.

The project focuses on:

- AutoCAD engineering drawing analysis
- Solid Edge reconstruction assistance
- Sheet metal reasoning and unfold analysis
- Assembly interference detection
- Manufacturing feasibility review
- Long-context engineering memory
- Engineering workflow collaboration

The system is designed to assist complex freezer and refrigeration equipment design workflows involving large CAD assemblies, manufacturing constraints, and iterative engineering reviews.

---

## Current Workflow Capabilities

### Drawing Analysis Agent

Responsible for:

- Parsing CAD drawings
- Detecting dimensions and layer structures
- Identifying bend edges and flange relationships
- Extracting assembly references
- Analyzing structural topology

### Sheet Metal Agent

Responsible for:

- Bend sequence analysis
- K-Factor estimation
- Unfold length prediction
- Manufacturing constraint reasoning
- Sheet metal process recommendations

### Manufacturing Review Agent

Responsible for:

- Manufacturing feasibility analysis
- Material compatibility checks
- Welding/process recommendations
- Foam layer and insulation analysis
- Structural process risk detection

### Assembly Check Agent

Responsible for:

- Collision detection
- Structural interference analysis
- Part matching validation
- Clearance verification
- Assembly relationship reasoning

---

## Workflow Architecture

```text
                         ┌────────────────────┐
                         │ CAD Engineering    │
                         │ Files (.dwg/.par) │
                         └─────────┬──────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │ Drawing Analysis Agent      │
                    │ - Dimensions                │
                    │ - Layers                    │
                    │ - Bend Structures           │
                    └──────────────┬──────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼

┌──────────────────┐   ┌──────────────────┐   ┌────────────────────┐
│ Sheet Metal      │   │ Assembly Check   │   │ Manufacturing      │
│ Agent            │   │ Agent            │   │ Review Agent       │
│                  │   │                  │   │                    │
│ - K-Factor       │   │ - Collision      │   │ - Process Review   │
│ - Unfold Logic   │   │ - Interference   │   │ - Material Check   │
│ - Bend Analysis  │   │ - Clearances     │   │ - Risk Analysis    │
└─────────┬────────┘   └─────────┬────────┘   └──────────┬─────────┘
          │                      │                       │
          └──────────────────────┼───────────────────────┘
                                 ▼

                   ┌──────────────────────────┐
                   │ Engineering Memory Layer │
                   │ - Historical Context     │
                   │ - CAD Knowledge Base     │
                   │ - Workflow Memory        │
                   └─────────────┬────────────┘
                                 ▼

                  ┌───────────────────────────┐
                  │ CAD Reconstruction &      │
                  │ Engineering Suggestions   │
                  └───────────────────────────┘
