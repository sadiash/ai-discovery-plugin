# AI Product Discovery Plugin

A Claude Code plugin that autonomously runs the **MIT Disciplined Entrepreneurship** 24-step validation framework for any product idea — generating Excel models, Word documents, and PowerPoint presentations along the way.

## What It Does

Solo founders and product teams waste months building products nobody wants. This plugin enforces rigorous validation before building anything. You describe your idea, and four AI agents work through the full MIT DE framework, pausing only at 6 human decision gates.

## How to Use

1. Create a new empty folder for your project and open it in Claude Code
2. Type `/start-discovery` and describe your product idea
3. The agents run autonomously through all 24 steps
4. Review and approve at each of the 6 human gates
5. All deliverables are saved directly into your project folder

To resume a paused project, simply open the folder again — the plugin detects `project-state.json` and picks up where it left off.

## The 6 Human Gates

The plugin runs autonomously except at these decision points:

| Gate | Step | Decision |
|------|------|----------|
| 1 | Step 2  | Confirm beachhead market selection |
| 2 | Step 5  | Validate end user profile and personas |
| 3 | Step 8  | Approve product specification |
| 4 | Step 15 | Confirm business model and pricing |
| 5 | Step 20 | Validate key assumptions |
| 6 | Step 22 | Approve MVP scope |

## Output Structure

Every project gets this folder structure with all deliverables:

```
your-project/
├── project-state.json
├── IDEA.md
├── PHASE-1-MARKET-SELECTION/
│   └── deliverables/
│       ├── market-segmentation-matrix.xlsx
│       └── tam-analysis.xlsx
├── PHASE-2-USER-RESEARCH/
│   └── deliverables/
│       ├── personas.docx
│       ├── user-journey-map.xlsx
│       └── interview-guide.docx
├── PHASE-3-VALUE-PROPOSITION/
│   └── deliverables/
│       ├── PRD.docx
│       └── feature-prioritization.xlsx
├── PHASE-4-BUSINESS-MODEL/
│   └── deliverables/
│       ├── tam-sam-som.xlsx
│       ├── ltv-cac-model.xlsx
│       ├── business-model-canvas.docx
│       ├── burn-rate-analysis.xlsx
│       ├── financial-projections.xlsx
│       └── investor-deck.pptx
├── PHASE-5-VALIDATION/
│   └── deliverables/
│       ├── assumption-matrix.xlsx
│       ├── mvp-scope.docx
│       ├── mvp-prioritization.xlsx
│       └── pmf-validation-report.docx
├── PHASE-6-EXECUTION/
│   └── deliverables/
│       ├── technical-roadmap.xlsx
│       ├── product-architecture-deck.pptx
│       ├── go-to-market-plan.docx
│       └── launch-checklist.xlsx
└── DELIVERABLES-SUMMARY/
    ├── executive-summary-deck.pptx
    ├── complete-discovery-report.docx
    └── next-steps.md
```

## Agents

| Agent | Responsibility | Steps |
|-------|---------------|-------|
| **Supervisor** | Orchestrates workflow, synthesizes outputs | All |
| **PM Market Strategist** | Market research, TAM, business model, pricing | 1–2, 9–18 |
| **UX Research Agent** | User interviews, personas, journey mapping | 3–6, 22 |
| **Architect Agent** | Product spec, MVP definition, technical planning | 7–8, 21, 23 |

## Installation

```bash
# Add the local marketplace
claude plugin marketplace add /path/to/claude-plugins

# Install the plugin
claude plugin install ai-product-discovery

# Restart Claude Code
```

## Requirements

- Claude Code with plugin support
- `anthropic-skills` (document-skills) installed for Excel, Word, and PowerPoint generation
- Brave Search MCP for real market data (optional but recommended)
