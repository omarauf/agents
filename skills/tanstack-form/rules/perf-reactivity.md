# Use Selectors with useStore

## Explanation
When subscribing to form state changes using the `useStore` hook, it is strongly recommended to use a selector. Omitting the selector causes the component to re-render on *any* state change in the form, leading to significant performance degradation. Additionally, avoid using `useField` just to achieve reactivity; it is designed to be used internally within `form.Field` components.

## Bad Example
```tsx
// ❌ Re-renders on any form state change, including properties you don't use
const store = useStore(form.store)

// ❌ Discouraged: using useField purely for reactivity outside a field component
const field = useField({ form, name: 'firstName' })
```

## Good Example
```tsx
// ✅ Correct use: selectively subscribe to only what is needed
const firstName = useStore(form.store, (state) => state.values.firstName)
const errors = useStore(form.store, (state) => state.errorMap)
```

## Context
Use this whenever you need to read specific form values or metadata outside of the immediate `form.Field` render prop contexts, while maintaining optimized rendering performance.