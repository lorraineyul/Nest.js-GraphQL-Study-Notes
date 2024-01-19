# Nest.js-GraphQL-Study-Notes
This is a note repo for learning Nest.js and GraphQL

## 1. NestJS, PostgreSQL and TypeORM Setup
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
