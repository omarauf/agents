---
name: tanstack-form
description: TanStack Form best practices for form handling, validation, and user experience. Activate when building form-heavy React applications.
---

# TanStack Form Best Practices

Comprehensive guidelines for implementing TanStack Form patterns in React applications. These rules optimize form handling, validation, and user experience.

## When to Apply

- Setting up form state and validation
- Implementing complex, nested, or array-based forms
- Optimizing form rendering performance
- Writing reusable form components
- Handling form submissions and external API integrations
- Managing dirty states and touched fields

## Rule Categories by Priority

| Priority | Category | Rules | Impact |
|----------|----------|-------|--------|
| CRITICAL | Reactivity & Perf | 2 rules | Prevents infinite loops and large-scale re-renders |
| CRITICAL | Validation | 1 rule | Ensures robust schema-based data integrity |
| HIGH | Form & Fields | 3 rules | Proper component structuring and configuration reuse |
| HIGH | Arrays | 1 rule | Prevents buggy list rendering |
| MEDIUM | Events | 1 rule | Better UX and native HTML interoperability |

## Quick Reference

### Reactivity & Performance (Prefix: `perf-`)

- `perf-reactivity` — Always use selectors with `useStore` to prevent unnecessary re-renders. Avoid `useField` for reactivity.
- `perf-subscribe` — Use `form.Subscribe` for fine-grained form state rendering (e.g., submit buttons).

### Validation (Prefix: `val-`)

- `val-schema` — Use standard schema libraries (e.g., Zod, Valibot) for validation instead of inline functions.

### Form & Fields (Prefix: `form-` / `field-`)

- `form-composition` — check if there is custom form composition in the codebase (e.g. `createFormHook`) and use it instead of base `useForm`.
- `form-options` — Use `formOptions` to share and define default configurations outside of the component.
- `field-render-prop` — Always use the `children` render prop correctly for `<form.Field>` to access `field.state` and API.

### Arrays (Prefix: `arr-`)

- `arr-mode` — Manage list data correctly using `mode="array"` and its provided helper methods like `pushValue` and `removeValue`.

### Events (Prefix: `evt-`)

- `evt-reset` — Handle native form reset behaviors gracefully to avoid overriding uncontrolled inputs unexpectedly.

## How to Use

Each rule file in the `rules/` directory contains:
1. **Explanation** — Why this pattern matters
2. **Bad Example** — Anti-pattern to avoid
3. **Good Example** — Recommended implementation
4. **Context** — When to apply or skip this rule

## Full Reference

See individual rule files in `rules/` directory for detailed guidance and code examples.


