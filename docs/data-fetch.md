# Data Fetch

We are going to display the user's input! Below `index.tsx` copy and paste the following code.

```typescript
interface FormData {
  title: string
  content: string
  id: string
}

const Home = ({ notes }: Notes) => {
  const [form, setForm] = useState<FormData>({
    title: '',
    content: '',
    id: ''
  })
```

```typescript
export const getServerSideProps: GetServerSideProps = async () => {
  const notes = await prisma.note.findMany({
    select: {
      title: true,
      id: true,
      content: true
    }
  })

  return {
    props: {
      notes
    }
  }
}
```
