<h1 align="center">Marketplace - a Blocket clone</h1>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#setup">Setup</a> •
  <a href="#screenshots">Screenshots</a>
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

## Setup

### Prerequisites

* [Git](https://git-scm.com) version >= 2.13
* Java JDK version >= 21
* [Node.js](https://nodejs.org) version >= 20
* A PostgreSQL DB instance set up with the provided ```schema.sql```
* (Optional) [Docker](https://www.docker.com/) for running backend tests

### Linux/macOS
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

Lastly, to run the project:
* Run ```cd backend && ./gradlew bootRun``` to start the backend server.
* Run ```cd frontend && npm run dev``` to start the frontend server.

If everything was successful:
* Frontend server @ http://localhost:3000
* Backend server @ http://localhost:8080

### Windows (Untested)
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

Lastly, to run the project: 
* Run: ```cd backend``` and then  ```gradlew.bat bootRun``` to start the backend server.
* Run: ```cd frontend``` and then ```npm run dev``` to start the frontend server.

If everything was successful:
* Frontend server @ http://localhost:3000
* Backend server @ http://localhost:8080

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
