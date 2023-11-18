###    🎲 Branches

- 02 🔥 [typescript+graphQl+prisma+postgres starter](https://github.com/bappasahabapi/bolg-app-graphQL-prisma-postgres-ts/tree/bappa/02/prisma-postgres-graphQL-typeScript-starter)
- 01 🔥 [typescript+graphQl server starter](https://github.com/bappasahabapi/bolg-app-graphQL-prisma-postgres-ts/tree/bappa/01/graphL-typescript-starter)

[server doc:](https://www.apollographql.com/docs/apollo-server/)
###   Task-1 [Project Initialization]
####    01. 
**command:**
-    `yarn init -y`
-    `yarn add @apollo/server graphql`
-    `yarn add typescript`
-    `yarn add @types/node`
-    `yarn add ts-node-dev`
-    `yarn add -D nodemon`

####    02.
    Then make a folder name `src/index.ts`
⬇️ write the code in the **index.ts**
```ts
const test:string="server is working..."
```
🔲 run in the terminal to check working or not
` npx ts-node-dev src/index.ts`

- Now go to the **package.json** file and add the script

      "scripts": {
      "dev":"nodemon --watch './**/*.ts' --exec 'ts-node' src/index.ts"
       },

```json
{
  "name": "Blog-app",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "scripts": {
    "dev":"nodemon --watch './**/*.ts' --exec 'ts-node' src/index.ts"
  },
  "dependencies": {
    "@apollo/server": "^4.9.5",
    "@types/node": "^20.9.0",
    "graphql": "^16.8.1",
    "ts-node-dev": "^2.0.0",
    "typescript": "^5.2.2"
  },
  "devDependencies": {
    "nodemon": "^3.0.1"
  }
}

```
🔲 Now run the command 
-    `yarn dev`

###   Task-2 [congigure graphQL code ]. 

#### 01. Setup apollo server 
- [based on this link setup code in index.ts](https://www.apollographql.com/docs/apollo-server/getting-started)

- write the code in the **index.ts** file and then run the command `yarn dev`
```typescript
//todo: Task-1

// const test:string="server is working...";
// console.log(test);

//todo: Task-2

import { ApolloServer } from '@apollo/server';
import { startStandaloneServer } from '@apollo/server/standalone';

// A schema is a collection of type definitions (hence "typeDefs")
// that together define the "shape" of queries that are executed against
// your data.
const typeDefs = `#graphql

  type Book {
    title: String
    author: String
  }
  type Query {
    books: [Book]
  }
`;

const books = [
    {
        title: 'The Awakening',
        author: 'Kate Chopin',
    },
    {
        title: 'City of Glass',
        author: 'Paul Auster',
    },
];

const resolvers = {
    Query: {
        books: () => books,
    },
};

const main = async () => {
    const server = new ApolloServer({
        typeDefs,
        resolvers,
    });

    const { url } = await startStandaloneServer(server, {
        listen: { port: 4000 },
    });

    console.log(`🚀  Server ready at: ${url}`);
}

main()

```

###   Task-3 [setup Prisma and postgres]. 

- [setup document link](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases-typescript-postgresql)
- **commands**
- `npx tsc --init` 
To make **tsconfig.json** and comment out 
    - `"rootDir": "./src", `
    - ` "outDir": "./dist",    `
- Next install prisma 
  - `yarn add prisma`

- For creating schema 
 - `npx prisma init`

After the command a prisma file is created and now connect the **postgres database**

####    postges connection:
go to the .env file and set the d

- `DATABASE_URL="postgresql://johndoe:randompassword@localhost:5432/mydb?schema=public"`
to ⬇️
- `DATABASE_URL="postgresql://postgres:postgres@localhost:5432/blog_db?schema=public"`

🔲 Now run the command 
-`npx prisma migrate dev`

**set up is done**-----------------

