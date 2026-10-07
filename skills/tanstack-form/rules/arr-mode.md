# Managing Lists with Array Fields

## Explanation
For managing lists of values (like a list of items/hobbies) within a form, explicitly use `<form.Field mode="array">`. This surfaces array-specific helper methods within the `children` render prop (`pushValue`, `removeValue`, `swapValues`, etc.) to dynamically modify arrays in a structured fashion.

## Bad Example
```tsx
// ❌ Manually handling array immutability and overwriting the full array state repeatedly.
<form.Field name="hobbies">
  {(field) => (
    <button onClick={() => field.handleChange([...field.state.value, { name: '' }])}>
      Add Hobby
    </button>
  )}
</form.Field>

```

## Good Example
```tsx
// ✅ Take advantage of mode="array" to access specialized array mutation methods.
<form.Field name="hobbies" mode="array">
  {(hobbiesField) => (
    <div>
      {/* Iterate over field data */}
      {hobbiesField.state.value.map((_, i) => (
        <form.Field
          key={i}
          name={`hobbies[${i}].name`}
          children={(field) => (
            <input
              value={field.state.value}
              onChange={(e) => field.handleChange(e.target.value)}
            />
          )}
        />
      ))}

      {/* Employ array helpers directly */}
      <button type="button" onClick={() => hobbiesField.pushValue({ name: "" })}>
        Add hobby
      </button>

      <button type="button" onClick={() => hobbiesField.removeValue(0)}>
        Remove First
      </button>
    </div>
  )}
</form.Field>
```

## Context
Use this pattern exclusively anytime you are dynamically collecting a sequence or array-based data model under a single form parent.