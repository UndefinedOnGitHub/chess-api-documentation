# OpenAPI Documentation for Chess.com

This is an [openapi](https://learn.openapis.org/) version [3.0.0](https://spec.openapis.org/oas/v3.1.0) for the public api.

### TLDR: This is the [JSON](https://raw.githubusercontent.com/UndefinedOnGitHub/chess-api-documentation/master/openapi.json), This is the [live viewer](https://htmlpreview.github.io/?https://github.com/UndefinedOnGitHub/chess-api-documentation/blob/master/index.html).

<hr>

## Basic Information

After looking at the documentation of **chess.c<span>om</span>** so many times it made me want to just take the initiative and construct the api in a proper format. Though unlikly I hope this may create a revitalization of the open source community with **chess.co<span>m</span>**. It appears that the public api has not been updated much, if at all, since 2022. I took the info quickly from the documentation page. There may be some mistakes. Please provide PRs to improve this json.

This whole project is all about the `openapi.json`. The rest of the project is just set dressing for this file. 

### [openapi.json](https://github.com/UndefinedOnGitHub/chess-api-documentation/blob/master/openapi.json)

```json
{
  "openapi": "3.0.0",
  "info": {
    "version": "2.0.0",
    "title": "Chess.com Public API reference",
    "contact": {
      "name": "Chess.com Public API",
      "url": "https://www.chess.com/news/view/published-data-api"
    },
    "description": "The PubAPI is a read-only ..."
  },
  "servers": [
    {
      "url": "https://api.chess.com/pub",
      "description": "Chess.com Public Api"
    }
  ],
  ...
```

## Using The Api
You can see a live local index.html version here:

[index.html](https://htmlpreview.github.io/?https://github.com/UndefinedOnGitHub/chess-api-documentation/blob/master/index.html)

or

Paste the JSON in one of these:
* [raw JSON link](https://raw.githubusercontent.com/UndefinedOnGitHub/chess-api-documentation/master/openapi.json)
* [Viewer 1](https://mrin9.github.io/OpenAPI-Viewer/#/load/)
* [Viewer 2](https://rapidocweb.com/examples/example2.html)

or

Go online and look up any openapi documentation viewer

## Development

## Structure

Use [openapi v3.1.0](https://spec.openapis.org/oas/v3.1.0)

### Openapi Validation
```bash
npx openapi-generator-cli validate -i ./openapi.json
```

### Live Debugging
* Simply host the project with any local server
* Edit [index.html](https://github.com/UndefinedOnGitHub/chess-api-documentation/blob/master/index.html) to reference the local json file