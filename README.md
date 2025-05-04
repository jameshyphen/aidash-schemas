# AiDash GraphQL Schemas

This repository contains GraphQL schemas used by both frontend and backend services of AiDash.

## Project Structure

```
aidash-schemas/
├── schemas/
│   ├── common/
│   │   ├── scalars.graphql      # Common scalar types
│   │   ├── enums.graphql        # Common enum types
│   │   └── pagination.graphql   # Pagination types and interfaces
│   ├── entities/
│   │   └── user.graphql         # User entity type definitions
│   └── schema.graphql           # Main schema file
├── .prettierrc                 # Prettier configuration
├── .prettierignore            # Prettier ignore rules
├── codegen.yml                # GraphQL code generation config
├── package.json               # NPM package configuration
├── pom.xml                    # Maven configuration
└── README.md
```

## Usage

These schemas are used to:
1. Generate TypeScript types for the frontend
2. Generate Java classes for the backend
3. Ensure type safety across the entire stack

## Development

### Local Development

1. Install dependencies:
```bash
npm install
```

2. Run linter for the GraphQL schemas:
```bash
npm run lint
```

3. Format the schemas:
```bash
npm run format
```

### Publishing

#### Maven Publishing

The project is configured to generate Java classes from GraphQL schemas using the `graphql-codegen-maven-plugin`.

##### Local Installation

To install the package locally (available in your local Maven repository):

```bash
mvn clean install
```

This will:
1. Generate Java classes from GraphQL schemas
2. Compile the generated classes
3. Install the package to your local Maven repository at:
   - `${HOME}/.m2/repository/com/aidash/aidash-graphql/1.3.0/`

##### Using the Maven Package

After installation, you can use the package in other Maven projects by adding:

```xml
<dependency>
    <groupId>com.aidash</groupId>
    <artifactId>aidash-graphql</artifactId>
    <version>1.3.0</version>
</dependency>
```

The generated classes will be available in the `com.aidash.graphql.model` package.

#### NPM Publishing

##### Local Installation

To generate and publish the package locally:

1. Install the npm packages:
```bash
npm i
```

2. Generate the typescript interfaces and create the local package:
```bash
npm run publish:local
```

3. The package will be available at:
   - `${HOME}/.npm-packs/aidash-graphql-schemas-1.3.0.tgz`

##### Using the NPM Package

To use the package in another npm-managed project:

```bash
npm i ${HOME}/.npm-packs/aidash-graphql-schemas-1.3.0.tgz
```
