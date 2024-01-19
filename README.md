# Nest.js-GraphQL-Study-Notes
This is a note repo for learning Nest.js and GraphQL

## 1. NestJS local dev environment setup
### NestJS
Create Project
```bash
npm i -g @nestjs/cli
nest new project-name
```

Run
```bash
npm run start:dev
```

### Postgres
1. [Setting up a local PostgreSQL database — with docker automation](https://medium.com/@gausmann.simon/nestjs-typeorm-and-postgresql-full-example-development-and-project-setup-working-with-database-c1a2b1b11b8f)

2. PostgreSQL database server on local machine
   
  Create Database
  ```sql
  CREATE DATABASE dbname;
  CREATE USER username WITH PASSWORD 'password';
  GRANT ALL PRIVILEGES ON DATABASE dbname TO username;
  ```


### TypeORM
```bash
npm install --save @nestjs/typeorm typeorm pg
```
