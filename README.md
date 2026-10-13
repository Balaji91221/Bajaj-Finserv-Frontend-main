# BFHL JSON Response Explorer

**Submit structured input and choose which parts of the API response to display.**

React · Axios · React Select

A frontend challenge submission by **Kelavath Balaji Naik · 21BCE9738**.

## What it does

The app provides a JSON input box, validates its syntax, posts the parsed object to a configured `/bfhl` API, and renders selected response fields. It demonstrates the boundary between form validation, an asynchronous request, and filtered presentation.

- JSON parsing errors are shown before a request is sent.
- API and network failures appear in the interface.
- A multi-select control filters **Alphabets**, **Numbers**, and **Highest Alphabet**.

## Run locally

Open the source directory with Node.js/npm installed:

```bash
npm install
npm start
```

Visit [localhost:3000](http://localhost:3000). `npm run build` creates the frontend bundle.

## Example workflow

Enter a JSON object accepted by your BFHL backend, for example:

```json
{"data":["A","b","1","2"]}
```

Click **Submit**, then choose one or more result categories. The frontend expects the response fields `alphabets`, `numbers`, and `highest_alphabet`.

## Request flow

```text
JSON text → syntax validation → Axios POST /bfhl
         → response state → selected fields → rendered output
```

[`src/App.js`](src/App.js) contains the form, validation, request, and response filtering. [`src/App.css`](src/App.css) controls presentation. The app was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Backend dependency

The API URL is currently embedded in `src/App.js`. This repository contains the frontend only; API availability, accepted input schema, and server-side processing depend on that external service. Update the endpoint for your own backend before deployment. JSON syntax validation does not validate the backend's complete request schema.
