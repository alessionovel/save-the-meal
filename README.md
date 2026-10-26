# SaveTheMeal

A web app against food waste: restaurants and food shops sell their leftover or close-to-expiry food as surprise **Meals** at a lower price, and customers buy them and pick them up in a given time slot.

University group project for a software engineering course: it goes from requirements analysis to a tested REST API with a web front end.

## Features

**Suppliers** (restaurants, shops)
- Register their store and log in
- Publish Meals with size, price and pickup time slot
- Review purchase requests from customers with food intolerances, then accept or reject them

**Customers**
- Browse suppliers and available Meals without an account
- Sign up and log in
- Buy a Meal, optionally stating food intolerances. In that case the Meal is held until the supplier confirms it is safe; if the supplier rejects the request, the Meal becomes available again
- Leave a review for stores where they bought a Meal

## Tech stack

Node.js · Express · MongoDB (Mongoose) · JWT authentication · Swagger (OpenAPI) · Jest + Supertest · HTML/CSS/JavaScript front end

## API

The REST API is documented with Swagger and served at `/api-docs` when the app is running.

| Resource | Endpoints |
| --- | --- |
| Meals | `GET/POST/DELETE /meal`, `GET/DELETE /meal/{id}` |
| Suppliers | `POST /fornitore/login`, `GET/POST/DELETE /fornitore`, `GET/DELETE /fornitore/{id}` |
| Users | `POST /utente/login`, `GET/POST /utente` |
| Reviews | `GET/POST /feedback`, `DELETE /feedback/{id}` |
| Purchases | `GET/POST /acquisto`, `GET/POST /acquisto/{id}` |

## Getting started

Requirements: Node.js and a MongoDB database (local or Atlas).

```bash
npm install
cp .env.example .env   # set MONGO_URI and SUPER_SECRET
npm start              # http://localhost:3000
npm test               # run the Jest test suite
```

## Project structure

```
backend/
├── app.js, server.js    Express app and server bootstrap
├── models/              Mongoose schemas
├── controllers/         Business logic and JWT checks
├── routes/              API routes
├── swagger.json         OpenAPI specification
└── *.test.js            Tests
frontend/                Customer and supplier pages
docs/                    Project deliverables (in Italian)
```

## Documentation

The project was delivered in five documents, all in Italian:

1. [Requirements analysis](docs/D1-requirements-analysis.pdf)
2. [Requirements specification](docs/D2-requirements-specification.pdf): use cases, functional and non-functional requirements
3. [Architecture](docs/D3-architecture.pdf): class diagram and OCL constraints
4. [Development](docs/D4-development.pdf): user flows, API documentation, testing
5. [Final report](docs/D5-final-report.pdf): team organisation and workload

## Team

- **Alessio Novel**: project lead, front end, API edge cases
- **Alessia Laghezza**: API development, class diagram
- **Anna Metelli**: analysis, front-end design, documentation

The original team repository is [SaveTheMeal/Web-API](https://github.com/SaveTheMeal/Web-API). The Heroku deployment it mentions is no longer online.

The code identifiers and the interface are in Italian.
