###    Commands

-  `npx prisma migrate dev`



###    🎲 Branches

- 03 🔥 [blog app user login+jwt](https://github.com/bappasahabapi/bolg-app-graphQL-prisma-postgres-ts/tree/log/03/v1/user-login)
- 02 🔥 [typescript+graphQl+prisma+postgres starter](https://github.com/bappasahabapi/bolg-app-graphQL-prisma-postgres-ts/tree/bappa/02/prisma-postgres-graphQL-typeScript-starter)
- 01 🔥 [typescript+graphQl server starter](https://github.com/bappasahabapi/bolg-app-graphQL-prisma-postgres-ts/tree/bappa/01/graphL-typescript-starter)

[server doc:](https://www.apollographql.com/docs/apollo-server/)



### Requirements of the blog app
`Technology Stack`:
- graphql
- typescript
- postgresql
- prisma

# Blog app

**A. Requirement**
- user can post and pulish blog content
- user can see post 
- authentication system
- user can see their own profile

**B. Table**

- **post**
    - id
    - title
    - content
    - authorId
    - createdAt
    - updatedAt
    - published

- **user**
    - id
    - name
    - email
    - password
    - createAt
    - updateAt
    - profile

- **profile**
    - id
    - bio
    - createAt
    - updateAt
    - userId



--



