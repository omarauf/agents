# Preventing Native Form resets

## Explanation
When employing the biological fallback functionalities like `<button type="reset">` alongside TanStack Form's programmatic `form.reset()`, the default HTML execution will conflict, potentially destroying form state. Always use `event.preventDefault()` to ensure TanStack explicitly manages form state clearing, or simply use `type="button"`.

## Bad Example
```tsx
// ❌ Neglecting native events triggers unpredictable behavior in uncontrolled components like <select> or specific bound elements.
<button
  type="reset"
  onClick={() => {
    form.reset()
  }}
>
  Reset
</button>
```

## Good Example
```tsx
// ✅ Neutralize the HTML event entirely prior to issuing programmatic reset
<button
  type="reset"
  onClick={(event) => {
    event.preventDefault()
    form.reset()
  }}
>
  Reset
</button>

// ✅ Or circumvent the type handler
<button
  type="button"
  onClick={() => form.reset()}
>
  Reset
</button>
```

## Context
This is required whenever designing form actions that clear or reset default field values alongside standard DOM `<form>` nodes.