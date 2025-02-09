<h1 align="center">Marketplace - a Blocket clone</h1>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#setup">Setup</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#future-improvements">Future improvements</a>
</p>

<div align="center">
  <table>
    <tr>
      <td>
        <img alt="Marketplace search page on desktop" src="https://github.com/Luxcorel/marketplace/assets/98045373/d0567864-cf00-4a22-abc1-56f18b857400">
      </td>
      <td>
        <img alt="Marketplace search page on mobile" src="https://github.com/Luxcorel/marketplace/assets/98045373/eec34145-5a56-4724-90f5-646fef91c767">
      </td>
    </tr>
    <tr>
      <td>
        <p>Search page on desktop</p>
      </td>
      <td>
        <p>Search page on mobile</p>
      </td>
    </tr>
  </table>
</div>

## Overview
This is a web app that allows users to buy and sell products through product listings. The design of the app is heavily inspired by Blocket (a Swedish website similar to Facebook marketplace). The application consists of a frontend made with the JavaScript framework Next.js and a backend made with the Java framework Spring Boot.

### Key features
* Create product listings with image(s), description, price etc.
* Search for product listings by various search criteria
* Subscribe to new listings in chosen product categories
* Purchase history
* UI for desktop & mobile

### Technologies used

#### Backend

| Name                                                  | Description                                 |
|-------------------------------------------------------|---------------------------------------------|
| [Spring Boot](https://spring.io/projects/spring-boot) | Java framework                              |
| [Test Containers](https://testcontainers.com/)        | Unit testing using Docker containers        |
| [Github Actions](https://docs.github.com/en/actions)  | CI: running unit tests and building project |

#### Frontend

| Name                                                  | Description                                        |
|-------------------------------------------------------|----------------------------------------------------|
| [Next.js](https://nextjs.org/)                        | Full-stack JavaScript framework                    |
| [Shadcn UI](https://github.com/shadcn-ui/ui)          | UI component library                               |
| [SWR](https://swr.vercel.app/)                        | Client-side data fetching library                  |
| [Tailwind](https://tailwindcss.com/)                  | CSS styling library                                |
| [Github Actions](https://docs.github.com/en/actions)  | CI: linting, format checking, and building project |

#### Hosting of this project

| Name                                                  | Description                                 |
|-------------------------------------------------------|---------------------------------------------|
| [Vercel](https://vercel.com/)                         | Frontend hosting                            |
| [Railway](https://railway.com/)                       | Backend and database hosting                |

## Setup

* [Prerequisites](#prerequisites)
* [Setup using Docker](#setup-using-docker)
* [Setup using Linux/macOS](#setup-using-linuxmacos)
* [Setup using Windows (Powershell)](#setup-using-windows-powershell)

### Prerequisites

* [Git](https://git-scm.com) version >= 2.13
* Java JDK version >= 21
* [Node.js](https://nodejs.org) version >= 20
* A PostgreSQL DB instance set up with the provided scripts in the ```db-init/``` directory
* (Optional) [Docker](https://www.docker.com/) for running backend unit tests or using the Docker setup

### Setup using Docker

> [!NOTE]
> This setup requires Docker to be installed.
> Make sure Docker is running before executing any of the following commands. 

Dockerfiles are provided in the backend and frontend modules, which can be run individually if desired. The following setup will use docker-compose to instantiate the frontend, the backend, and a PostgreSQL database. These instances are configured using the ```docker-compose.yml``` file, which can be customized. 

Download, build, and run in one command:

<details>
  <summary>Linux/macOS</summary>
  
  ```bash
  git clone --recurse-submodules https://github.com/luxcorel/marketplace && \
  cd ./marketplace && \
  cd ./backend && \
  ./gradlew build -x test && \
  cd .. && \
  docker compose up --build
  ```

</details>

<details>
  <summary>Windows (Powershell)</summary>
  
```powershell
Invoke-Command -ScriptBlock {
$ErrorActionPreference="Stop";
git clone --recurse-submodules https://github.com/luxcorel/marketplace ; `
cd ./marketplace ; `
cd ./backend ; `
./gradlew.bat build -x test ; `
cd .. ; `
docker compose up --build
}
```

</details>

Run already downloaded and built modules:
```bash
docker compose up --build
```

If everything was successful:
* Frontend server @ http://localhost:3000
* Backend server @ http://localhost:8080

### Setup using Linux/macOS
Download & build:
```bash
git clone --recurse-submodules https://github.com/luxcorel/marketplace && \
cd ./marketplace && \
cd ./backend && \
mv ./.env.example ./.env && \
./gradlew build -x test && \
cd .. && \
cd ./frontend && \
mv ./.env.example ./.env && \
npm install && \
cd ..
```

After the command above finishes, required environment variables need to be set:  
* Open ```backend/.env``` with a text editor and follow the instructions in the file.
* Open ```frontend/.env``` with a text editor and follow the instructions in the file. 

#### Running the project
* Run ```cd backend && ./gradlew bootRun``` to start the backend server.
* Run ```cd frontend && npm run dev``` to start the frontend server.

If everything was successful:
* Frontend server @ http://localhost:3000
* Backend server @ http://localhost:8080

#### Run backend tests (optional)
> [!NOTE]
> Docker must be installed and running for unit tests to be run. 

* Run: ```cd backend``` and then  ```./gradlew test``` to run the backend tests.

### Setup using Windows (Powershell)
Download & build:
```powershell
Invoke-Command -ScriptBlock {
$ErrorActionPreference="Stop";
git clone --recurse-submodules https://github.com/luxcorel/marketplace ; `
cd .\marketplace ; `
cd .\backend ; `
ren .\.env.example .\.env ; `
.\gradlew build -x test ; `
cd .. ; `
cd .\frontend ; `
ren .\.env.example .\.env ; `
npm install ; `
cd ..
}
```

After the command above finishes, required environment variables need to be set:
* Open ```backend\.env``` with a text editor and follow the instructions in the file.
* Open ```frontend\.env``` with a text editor and follow the instructions in the file. 

#### Running the project
* Run: ```cd backend``` and then  ```gradlew.bat bootRun``` to start the backend server.
* Run: ```cd frontend``` and then ```npm run dev``` to start the frontend server.

If everything was successful:
* Frontend server @ http://localhost:3000
* Backend server @ http://localhost:8080

#### Run backend tests (optional)
> [!NOTE]
> Docker must be installed and running for unit tests to be run. 

* Run: ```cd backend``` and then  ```gradlew.bat test``` to run the backend tests.

## Screenshots

<div>
<div align="center">
  <table>
    <tr>
      <td>
        <img alt="Creating a product listing" src="https://github.com/Luxcorel/marketplace/assets/98045373/01f93c78-0740-4333-b665-83dbdd010bba">
      </td>
    </tr>
    <tr>
      <td>
        <p>Creating a product listing</p>
      </td>
    </tr>
  </table>
</div>

<div align="center">
  <table>
    <tr>
      <td>
        <img alt="Watchlist page" src="https://github.com/Luxcorel/marketplace/assets/98045373/7292f95d-087c-4461-a76a-34ebb58b3c36">
      </td>
    </tr>
    <tr>
      <td>
        <p>Watchlist page - subscribe to new posts in chosen categories</p>
      </td>
    </tr>
  </table>
</div>

<div align="center">
  <table>
    <tr>
      <td>
        <img alt="Profile page" src="https://github.com/Luxcorel/marketplace/assets/98045373/2ee0e98f-cdf1-4c88-9bd2-4583bd7b21b4">
      </td>
    </tr>
    <tr>
      <td>
        <p>Profile page</p>
      </td>
    </tr>
  </table>
</div>

## Future improvements

- Rate limiting
- Captcha for the signup endpoint
- Open graph metadata and other SEO related features
- Image hosting on a CDN
- Pagination on search page
- Chat feature between buyers and sellers
