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
