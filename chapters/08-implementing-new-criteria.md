# Chapter 8: Implementing New Success Criteria

## Focus Not Obscured (2.4.11 AA)
Ensure keyboard focus indicators are never hidden.

**GitHub PR Example**: In a PR diff view, ensure the focused line highlight remains visible when tooltips or floating elements appear.

**Implementation Example (CSS)**
```css
:focus {
  outline: 3px solid #0066ff;
  outline-offset: 4px;
  z-index: 9999;
}
```

## Dragging Movements (2.5.7 AA)
In GitHub's drag-and-drop file reordering or kanban boards, provide button-based alternatives.

**Realistic PR Pattern**: Add "Move Up / Move Down" buttons alongside drag handles.

## Target Size (2.5.8 AA)
Make reaction buttons, merge buttons, and comment icons larger.

## Accessible Authentication
Replace complex CAPTCHAs with passkeys or email links in GitHub login flows.

## Community PR Examples
- Search GitHub for issues labeled `accessibility` in repos like `github/accessibility` or community forks.
- Example: Improving focus management in modals during code review.

## General Strategy
- Audit with axe-core
- Test with NVDA/VoiceOver
- Submit accessibility-focused PRs to open-source repos.