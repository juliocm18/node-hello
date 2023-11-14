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


8. Start the api in development mode
   ```sh
    xxxxxxxxx
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
    │   ├── lambda-rule-processor
    │   ├── services
    │   ├── swagger-ui
    │   ├── utils


### Migrations

   - Run docker locally
   ```sh
    docker build - < Dockerfile
    
   ```
   - Run Database server
   ```sh
   docker compose up -d
   ```
   - Go to packages/database folder and run the migrations
   ```sh
    cd packages/database/ && yarn run prisma:migrate    
   ```
   - Generate Models
   ```sh
   yarn run prisma:generate
   ```


### Seeders
> **Note**:
> To generate seeds xxx.
 


## Documentation

### Swagger
Swagger documentation can be accessed running the application locally and navigating to `<<base-url>>/swagger` in a web browser.

## Team's standards

- [SW Standards & Best Practices](#)
- [Branching strategy](#)
- [PR Template](./pr-template.md)

## Contact

Author: Amazing **Sweatworks** Team
