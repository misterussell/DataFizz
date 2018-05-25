# All My Books Are Packed - App

## Problem

Extract data from HTML files such that a MVP meets the following requirements:

Returns, at minimum, the following extracted data:

- Title
- Author
- Price
- Shipping Weight
- ISBN-10

This data is to be formatted in a json document that represents N boxes for shipping, such that no box of boxes is more than 10 pounds.

Document structure:
```
{
    "box": {
        "id": 1,
        "totalWeight": "1.1 pounds",
        "contents": [
            {
                "title": "The Great Big Beautiful Tomorrow",
                "author": "Cory Doctorow",
                "price": "$9.82 USD",
                "shipping_weight": "1.1 pounds",
                "isbn-10": 1604864044
            }

            . . .
        ]
    }

    . . .
}
```

### Additional Application Concerns

`EXTENSIONS.txt` - a document that notes app extensibility to handle:
1. Domains beyond Amazon.com.
2. Non-book products.
3. Parse and ship of 2,000,000 books in polynomial time.

### Reviewing Concerns
1. Code readability and reusability (how "productized" your code is)
2. Practical and sensible use of third-party code
3. The computational efficiency of your sorting algorithm

#### How to install/run
`npm install npm@latest -g`

`yarn start`/`npm start` to start dev server with hot reload, it's live on `localhost:3000`.

`yarn run build`/`npm run build` to build prod bundle, it includes both treeshaking and uglify to optimize the code as much as possible.

`yarn test`/`npm test` run the tests with Jest and Enzyme, by default the test included only check for the correct render of base components & routes, all are passing.

_Note: node scripts start must be run from the root/app folder._

#### Project structure

```
*root project folders*
├── app
  |
  ├── */src/*
  │   ├── */assets/* where images etc... are stored
  │   ├── */containers/* react-router jsx pages
  |   ├── */data/* saved HTML files to scrape
  │   ├── *App.jsx* main layout
  │   ├── *Routes.jsx* front-end routes
  │   ├── *index.html* entry point
  │   ├── *index.jsx* javascript entry point
  │   ├── *style.scss* styling
  │   └── */tests/* contains test environment (Jest + Enzyme)
  │       ├── */__mock__/* contains setup to provide a valid path for imports
  │       ├── */_tests__/* the actual tests
  │       └── *setup.js* setup for enzyme for react 16
  ├── *package.json* the whole package.json with every dependency and script, no hidden packages
  ├── *.eslintrc* eslint config
  ├── *.babelrc* babel config (polyfills)
  ├── *webpack.config.js* webpack config, it has a dev and prod environment
  └── *README.md* this file

```

#### Tests


#### Eslint

This project uses AirBnB Javascript specs.
