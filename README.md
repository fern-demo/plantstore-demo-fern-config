# Plantstore Demo Fern Configuration

This repository contains your Fern Configuration:

- [OpenAPI spec](./fern/openapi/external/universal-api-v1.yaml)
- [OpenAPI Overrides](./fern/openapi/external/openapi-overrides.yml)
- [SDK generator config](./fern/generators.yml)

## Setup

```sh
npm install -g fern-api
```

## Validating your API Definition

To validate your API, run:

```sh
fern check
```

## Updating Documentation

### Local Development Server

To run a local development server with hot-reloading you can run the following command

```sh
fern docs dev
```

### Hosted URL

To update your documentation on a hosted URL, run
```
# npm install -g fern-api
fern generate --docs
```
To preview your documentation, run
```
# npm install -g fern-api
fern generate --docs --preview
```
The repository contains GitHub workflows that will automatically run these commands for you. For example, when you make a PR a preview link will be auto-generated and when you merge to main the docs site will update.

## Managing SDKs

### Deploying your SDKs

To deploy your SDKs, simply run the `Release <sdk-language> SDK` GitHub Action with the desired version for the release. Under the hood, this leverages the Fern CLI:

```sh
fern generate --group <sdk-language>
```

### Developing SDKs

You can also regenerate the SDKs locally by running:

```sh
fern generate --group <sdk-language> --preview --log-level debug
```
