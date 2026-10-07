# Use App-Specific Form Composition over useForm

## Explanation
If the codebase contains a custom form composition setup (typically instantiated via `createFormHook` and `createFormHookContexts`), you must use the exported custom form hook (e.g., `useAppForm`) instead of the base `useForm` from `@tanstack/react-form`. Custom form hooks reduce boilerplate, pre-bind custom field and form UI components, and enforce type safety at an application-wide level. 

Always scan the codebase for a shared `form-context.ts` or similar setup before initializing new forms.

## Bad Example
```tsx
// ❌ Ignoring existing form-composition setups and manually wiring up base forms
import { useForm } from '@tanstack/react-form'
import { TextField } from '../components/TextField'

function App() {
  const form = useForm({
    defaultValues: { firstName: '' },
  })

  return (
    <form.Field name="firstName">
      {(field) => <TextField field={field} label="First Name" />}
    </form.Field>
  )
}
```

## Good Example
```tsx
// ✅ Utilizing the custom exported query hooks and bound sub-components
// (Assuming these are exported from a centralized form hook factory)
import { useAppForm } from '../hooks/form'

function App() {
  const form = useAppForm({
    defaultValues: { firstName: '' },
  })

  // AppForm and AppField come pre-bound with UI components and context!
  return (
    <div>
      <form.AppField name="firstName">
        {(field) => <field.TextField label="First Name" />}
      </form.AppField>
      <form.AppForm>
        <form.SubscribeButton label="Submit" />
      </form.AppForm>
    </div>
  )
}
```

## Context
Apply this rule whenever you create or modify forms in an environment where TanStack form composition tools (`createFormHook`, `withForm`, etc.) have already been configured.