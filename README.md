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
2. [NestJS doc](https://docs.nestjs.com/techniques/configuration)
3. PostgreSQL database server on local machine
   
* Create Database
```sql
CREATE DATABASE dbname;
CREATE USER username WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE dbname TO username;
```
```bash
psql -d dbname
```
```sql
CREATE TABLE tablename (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL
);
```

### TypeORM
```bash
npm install --save @nestjs/typeorm typeorm pg
```
```typescript
// app.module.ts

// add import
import { TypeOrmModule } from '@nestjs/typeorm';

@Module({
  imports: [
	// add TypeOrm module, warning: in production, don't expose password
	// one option is to hide the password in environment variables
    TypeOrmModule.forRoot({
      type: 'postgres',
      host: 'localhost',
      port: 5432,
      username: 'username',
      password: 'password',
      database: 'dbname',
      entities: [tablename],
	  // for local only
	  // setting this flat to true in production may lose data
      synchronize: true,
    }),
  ],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}
```
