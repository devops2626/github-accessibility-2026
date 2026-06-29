# Chapter 6: Technical Implementation Guide

## AI Semantic Narratives
- Integrate on-device LLMs (e.g., via WebLLM or browser extensions).
- Prompt engineering for diff summaries: "Describe changes in natural language for screen readers."

**Example Prompt Snippet (JavaScript)**
```js
async function summarizeDiff(diffText) {
  const prompt = `Convert this code diff into a clear, spoken summary for screen reader users:
${diffText}`;
  // Call LLM API or on-device model
  return await llm.generate(prompt);
}
```

## Core Semantic Mode
- Server-side rendering fallback with ARIA labels.
- Full keyboard navigation using standard HTML elements.

**Example ARIA-Enhanced Modal (HTML)**
```html
<div role="dialog" aria-labelledby="modal-title" aria-modal="true">
  <h2 id="modal-title">Pull Request Review</h2>
  <!-- Content -->
  <button onclick="closeModal()" aria-label="Close dialog">✕</button>
</div>
```

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
        with:
          fail-on: critical
```

## CLI Enhancements
Extend `gh` with text-based graph outputs using libraries like `graphviz` (text mode) or custom ASCII trees.

**Example CLI Output for Dependency Graph**
```
Root Project
├── Package A (updated)
│   └── Dependency X
└── Package B (new)
```

## ARIA & Semantic HTML Best Practices
- Proper `role`, `aria-label`, and live regions for dynamic updates.
- Focus management in modals and SPAs.

**Live Region Example**
```html
<div aria-live="polite" id="status"></div>
<script>
  document.getElementById('status').textContent = 'PR merged successfully';
</script>
```