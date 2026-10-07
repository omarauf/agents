# Use form.Subscribe for Fine-Grained Refreshes

## Explanation
To optimize your form's rendering performance, particularly for elements like submit buttons that rely on broad form states (`canSubmit`, `isSubmitting`), use the `form.Subscribe` component. This limits the re-renders to only the isolated chunk of UI rather than the entire form component.

## Bad Example
```tsx
// ❌ Forces the entire parent component to re-render merely to update the button state
const isSubmitting = useStore(form.store, (state) => state.isSubmitting)
const canSubmit = useStore(form.store, (state) => state.canSubmit)

return (
  <form onSubmit={/* ... */}>
    {/* ... fields ... */}
    <button type="submit" disabled={!canSubmit}>
      {isSubmitting ? '...' : 'Submit'}
    </button>
  </form>
)
```

## Good Example
```tsx
// ✅ Isolates the subscription to exactly what needs it, keeping the rest of the form untouched
return (
  <form onSubmit={/* ... */}>
    {/* ... fields ... */}
    <form.Subscribe selector={(state) => [state.canSubmit, state.isSubmitting]}>
      {([canSubmit, isSubmitting]) => (
        <button type="submit" disabled={!canSubmit}>
          {isSubmitting ? "..." : "Submit"}
        </button>
      )}
    </form.Subscribe>
  </form>
)
```

## Context
Apply this rule to dynamic UI parts reacting to form-level meta states (like error summaries, validity statuses, or submission buttons) to minimize performance hits on large or complex forms.