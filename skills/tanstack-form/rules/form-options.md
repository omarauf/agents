# Use formOptions for Shared Configuration

## Explanation
You can customize and abstract out your form configurations utilizing the `formOptions` function. These options act as a single source of truth allowing them to be shared across multiple standalone forms, making the codebase more modular and reducing boilerplate when generating common forms.

## Bad Example
```tsx
// ❌ Defining default configurations directly inside the instance multiple times
const form1 = useForm({
  defaultValues: { firstName: '', lastName: '', hobbies: [] },
  onSubmit: async ({ value }) => { /* ... */ }
})

const form2 = useForm({
  defaultValues: { firstName: '', lastName: '', hobbies: [] },
  onSubmit: async ({ value }) => { /* ... */ }
})
```

## Good Example
```tsx
// ✅ Extract form configuration, ensuring types and configs are reusable
const defaultUser = { firstName: '', lastName: '', hobbies: [] }

const formOpts = formOptions({
  defaultValues: defaultUser,
})

const form1 = useForm({
  ...formOpts,
  onSubmit: async ({ value }) => { console.log(value) },
})

const form2 = useForm({
  ...formOpts,
  onSubmit: async ({ value }) => { /* Handle differently */ },
})
```

## Context
When declaring multiple configurations with overlapping structures (e.g., matching shapes but varying submit targets, or abstracting validation options universally across your app context).