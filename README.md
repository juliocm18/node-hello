<!-- PROJECT LOGO -->
<br />
<p align="center">
    <img src="tivity-logo.png" alt="Logo" width="80%">
</p>

# Backend Project

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
      <a href="#usage">Usage</a>
      <ul>
        <li><a href="#directory-structure">Directory structure</a></li>
        <li><a href="#migrations">Migrations</a></li>
        <li><a href="#seeders">Seeders</a></li>
      </ul>
    </li>
    <li>
      <a href="#configure-ngrock">Configure Ngrock</a>
    </li>
    <li>
      <a href="#locust-deploy">Locust Deploy</a>
    </li>
    <li>
      <a href="#documentation">Documentation</a>
      <ul>
        <li><a href="#swagger">Swagger</a></li>
      </ul>
    </li>
    <li><a href="#teams-standards">Team's Standards</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

## About The Project
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

### Built With

- [NodeJS](https://nodejs.org/es/)
- [Pulumi](https://www.pulumi.com/)
- [Prisma](https://www.prisma.io/)
- [PostgreSQL](https://www.postgresql.org/)
- [Docker](https://www.docker.com/)
- [Swagger](https://swagger.io/)
- [Jest](https://jestjs.io/)
- [Json Web Token](https://jwt.io/)

## Getting Started

### Prerequisites
In order to run the application you must have the following tools installed:

- **Node 16.x LTS**, in case you don't have it you can follow the instructions to install it with [NVM](https://github.com/nvm-sh/nvm)

- **Docker and docker-compose**, in case you don't have it you can follow the [instructions to install](https://docs.docker.com/engine/install/)


### Installation

1. Clone the repo with token
   
   ```sh
    git clone https://{githubUser}:{token}@github.com/SweatWorks/revenue-cycle-api.git  
   ```
   
3. Locate in the project folder

   ```sh
    cd revenue-cycle-api/
   ```

4. copy the example.env file to a new file called .env and update the env variable values.


5. Install project dependencies
   ```sh
    yarn install
   ```

6. Run the database migrations
    ```sh
    npm run migration:local:run
   ```

7. Start the api in development mode
   ```sh
    yarn run dev
   ```

## Usage

### Directory structure

Inside of the application you will find a src folder with the following structure:
    
    src
    ├── docs
    ├── packages
    │   ├── database
    │   ├── get-health
    │   ├── ingest-s3-data
    │   ├── ingest-s3-data
    ├── app.ts
    ├── index.ts
        │   │   ├── aws
    │   │   ├── encrypt
    │   │   ├── middleware
    │   │   ├── typeorm
    │   │   ├── http    
    │   │   ├── presentation


### Migrations

- To generate a migration file run the command for that application:

  ```sh
  npm run migration:generate -- src/migrations/{name-of-file}
  ```
- To generate a migration file run the command for that application:

  ```sh
  npm run migration:run
  ```

  where `name-of-file` is the name of the migration and it's a mandatory attribute. The naming convention is the ticket ID that matches the name of the branch in lowercase. Example: `npm run migration:generate -- src/migrations/{name-of-file}`. This command generates a migration file
  located in the `src/database/migrations` folder.

  > **Note**: Run all existing migrations first before generating a new one.

- To abort the last migration run the command for that application:
  ```sh
  migration:local:revert
  ```

You should see the following content inside your migration:

  ```typescript
    import {MigrationInterface, QueryRunner} from "typeorm";

    export class PostRefactoringTIMESTAMP implements MigrationInterface {

        async up(queryRunner: QueryRunner): Promise<void> {

        }

        async down(queryRunner: QueryRunner): Promise<void> {

        }

  ```

There are two methods you must fill with your migration code: up and down. up has to contain the code you need to perform the migration. down has to revert whatever up changed. down method is used to revert the last migration. [Read more](https://typeorm.io/#/migrations/creating-a-new-migration)


### Seeders
> **Note**:
> To generate seeds that populate the database you should define what kind of seed you need.
 

- To generate a master data seeders:
File location: src/database/seeds/main-data.seeder.ts
```sh
npm run seed:run
```

- To generate a custom data seeders: (For Data testing)
File location: src/database/seeds/custom-data.seeder.ts
```sh
npm run seed:custom:run
```

### Configure Ngrock

- To use ngrok with your API in the Windows console, follow these steps:

- Download ngrok: Go to the official ngrok website (https://ngrok.com/) and download the corresponding Windows version.

- Unzip the file: Extract the downloaded ZIP file to a convenient location on your hard drive.

- Open the command window: Open the Windows command window. You can do this by pressing the Windows key + R, typing "cmd" and then pressing Enter.

- Configure your session
```sh
ngrok config add-authtoken {token}
```

- To start a HTTP tunnel forwarding to your local port {xxx}, run this next:

```sh
ngrok http 3001
```

### Locust Deploy
> **Note**:
> To deploy locust server you need deploy the docker image and configure de hostUrl with *ngrok*.
> Files location: /locust/

```sh
docker compose up -d --scale slave=3
```
- To configure the temporal domain generated by ngrok you need update the **docker-compose** file.
```sh
version: "3"
services:
  master:
    container_name: "maestro"
    build: .
    ports:
      - "8089:8089"
    command: "--host={ngrokDomain} --master"
  slave:
    build: .
    command: "--host={ngrokDomain} --slave  --master-host=maestro"
```

## Documentation

### Swagger
Swagger documentation can be accessed running the application locally and navigating to `<<base-url>>/swagger` in a web browser.

## Team's standards

- [SW Standards & Best Practices](#)
- [Branching strategy](#)
- [PR Template](./pull-request.md)

## Contact

Author: Amazing **PowerBizz** Team
