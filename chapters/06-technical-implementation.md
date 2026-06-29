# Chapter 6: Technical Implementation Guide

## AI Semantic Narratives
- Integrate on-device LLMs (e.g., via WebLLM or browser extensions).
- Prompt engineering for diff summaries: "Describe changes in natural language for screen readers."

## Core Semantic Mode
- Server-side rendering fallback with ARIA labels.
- Full keyboard navigation using standard HTML elements.

## Accessibility CI/CD
Example GitHub Action:
```yaml
name: Accessibility Audit
on: [pull_request]
jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run axe-core
        uses: axe-core/axe-github-action@v1
```

## CLI Enhancements
Extend `gh` with text-based graph outputs using libraries like `graphviz` (text mode) or custom ASCII trees.

## ARIA & Semantic HTML Best Practices
- Proper `role`, `aria-label`, and live regions for dynamic updates.
- Focus management in modals and SPAs.