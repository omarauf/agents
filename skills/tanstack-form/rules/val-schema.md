# Prefer Standard Schema Libraries for Validation

## Explanation
TanStack Form offers built-in support for the Standard Schema specification, allowing you to seamlessly integrate robust domain models using libraries like Zod, Valibot, or ArkType. This is preferred over hand-rolled validation functions, as it significantly enhances type safety, guarantees correctness, and scales better.

## Bad Example
```tsx
// ❌ Hand-rolled inline validation is prone to errors, hard to maintain, and lacks reusability.
<form.Field
  name="age"
  validators={{
    onChange: ({ value }) => {
      if (!value) return "Age is required";
      if (value < 13) return "You must be 13 to make an account";
      return undefined;
    },
  }}
>
  {(field) => <input type="number" {...field} />}
</form.Field>
```

## Good Example
```tsx
// ✅ Leverage standard schema solutions (e.g. Zod) for consistent data modeling.
import { z } from 'zod'

const userSchema = z.object({
  age: z.number().gte(13, 'You must be 13 to make an account'),
})

function App() {
  const form = useForm({
    defaultValues: { age: 0 },
    validators: {
      onChange: userSchema,
    },
  })
  
  return (
    <form.Field name="age">
      {(field) => {
        return <input type="number" {...field} />;
      }}
    </form.Field>
  )
}
```

## Context
Adopt this when setting up field constraints, form-level validation, or shared data boundaries between your client and API layers.