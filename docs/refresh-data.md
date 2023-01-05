# Refresh Data

By default the browser will not refresh when it receives a data, add the following code `index.tsx` to refresh the data.

```typescript
const refreshData = () => {
  router.replace(router.asPath)
}

async function create(data: FormData) {
  try {
    fetch('http://localhost:3000/api/create', {
      body: JSON.stringify(data),
      headers: {
        'Content-Type': 'application/json'
      },
      method: 'POST'
    }).then(() => {
      setForm({ title: '', content: '', id: '' })
      refreshData()
    })
  } catch (error) {
    console.log(error)
  }
}
```
