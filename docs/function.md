# Create function

This is the part where we can create the note. Copy the code `index.tsx` below the useState.

```typescript
async function create(data: FormData) {
  try {
    fetch("http://localhost:3000/api/create", {
      body: JSON.stringify(data),
      headers: {
        "Content-Type": "application/json",
      },
      method: "POST",
    }).then(() => setForm({ title: "", content: "", id: "" }));
  } catch (error) {
    console.log(error);
  }
}
```

# Handle Submit

Let's create a function to the onSubmit we created. Copy the code `index.tsx` below the _async function create_.

```typescript
const handleSubmit = async (data: FormData) => {
  try {
    create(data);
  } catch (error) {
    console.log(error);
  }
};
```

Add this inside the form tag.

```typescript
<form
  onSubmit={(e) => {
    e.preventDefault();
    handleSubmit(form);
  }}
>
  ...
</form>
```
