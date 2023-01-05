# Prisma

We use prisma as our database.

## Commands

Install prisma

```sh
npm install prisma --save-dev
npx prisma init
```

## Connection details

**Syntax**

```env
mysql://USER:PASSWORD@HOST:PORT/DATABASE
```

- `HOST` - `localhost`
- `PORT` - `3306`
- `USER` - name of your database user
- `PASSWORD` - password of your database user
- `DATABASE` - name of the database you want to use

## Create a model

```prisma
model Note {
  id Int @id @default(autoincrement())
  title String
  content String
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}
```

## Useful commands

```sh
npx prisma db push
npx prisma studio
npm install @prisma/client
npx prisma generate
```

# Prisma Client

Create a folder `lib` and inside the folder create a file `prisma.ts` and add the following:

```typescript
import { PrismaClient } from '@prisma/client'

declare global {
  var prisma: PrismaClient | undefined
}

export const prisma = global.prisma || new PrismaClient()

if (process.env.NODE_ENV !== 'production') global.prisma = prisma
```

The code above will be used to gain access to the database whatever we want.
