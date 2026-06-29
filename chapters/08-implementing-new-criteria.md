# Chapter 8: Implementing WCAG 2.2 New Success Criteria

## Focus Not Obscured (2.4.11 AA)
Ensure keyboard focus indicators are never hidden by overlapping content.

**Implementation Example (CSS)**
```css
:focus {
  outline: 3px solid #0066ff;
  outline-offset: 4px;
  z-index: 9999; /* Prevent obscuring */
}
```

## Dragging Movements (2.5.7 AA)
Provide single-pointer alternatives to drag-and-drop (e.g., buttons for reordering files).

## Target Size (2.5.8 AA)
Minimum 24x24 CSS pixels for interactive targets.

## Accessible Authentication (3.3.8 AA)
Avoid CAPTCHA; use passwordless or simple alternatives.

## General Strategy
- Audit with axe-core
- Progressive enhancement
- Test with real screen readers (NVDA, VoiceOver)