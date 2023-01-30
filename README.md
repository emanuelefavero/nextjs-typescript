# Typescript in NextJS

> Learn more about [Typescript in NextJS](https://nextjs.org/docs/basic-features/typescript)

This is a cheat sheet repository for Typescript in NextJS

## Example Projects

- [NextJS Blog TypeScript](https://github.com/emanuelefavero/nextjs-blog-typescript)

## Create a new NextJS App with TypeScript

- `npx create-next-app APP-NAME --typescript`

#### Create a new NextJS App with TypeScript and ESLint

- `npx create-next-app APP-NAME --typescript --eslint`

## Add Typescript to an existing NextJS App

Create a `tsconfig.json` file in the root of the project (`touch tsconfig.json`)

> NextJS will automatically detect and configure this file for you after you run `npm run dev` or `npm run build`

Alternatively, you can:

- `npm install --save-dev typescript @types/react @types/node`

## **The @ alias**

- Remember to add the @ alias for the root folder in `jsconfig.json` or `tsconfig.json`:

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      // Use @ as an alias for the root directory
      "@/*": ["./*"]
    }
  }
}
```

> Remember also to rename your files from `.js` to `.ts` and `.tsx`

## Typescript strict mode

- Strict mode is turned off by default in NextJS, when you feel comfortable with Typescript you can turn it on by adding the following to your `tsconfig.json` file:

```json
{
  "compilerOptions": {
    "strict": true
  }
}
```

## **NextJS Typescript types**

- Static Site Generation (SSG) and Server-side Rendering (SSR)

```ts
import { GetStaticProps, GetStaticPaths, GetServerSideProps } from 'next'

export const getStaticProps: GetStaticProps = async (context) => {
  // ...
}

export const getStaticPaths: GetStaticPaths = async () => {
  // ...
}

export const getServerSideProps: GetServerSideProps = async (context) => {
  // ...
}
```

- API Routes

```ts
import type { NextApiRequest, NextApiResponse } from 'next'

export default function handler(req: NextApiRequest, res: NextApiResponse) {
  res.status(200).json({ name: 'John Doe' })
}
```

- Custom App

```ts
import type { AppProps } from 'next/app'

export default function MyApp({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />
}
```

&nbsp;

---

&nbsp;

[**Go To Top &nbsp; ⬆️**](#demo)
