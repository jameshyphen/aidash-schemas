# AiDash GraphQL Schemas

This repository contains GraphQL schemas used by both frontend and backend services of AiDash.

## Structure

- `schemas/` - Contains all GraphQL schema definitions
  - `common/` - Common types and scalars
  - `entities/` - Entity type definitions
  - `inputs/` - Input type definitions
  - `queries/` - Query type definitions
  - `mutations/` - Mutation type definitions

## Usage

These schemas are used to:
1. Generate TypeScript types for the frontend
2. Validate GraphQL operations on the backend
3. Ensure type safety across the entire stack

## Development

To add new types or modify existing ones:
1. Add or modify the schema files in the appropriate directory
2. Update the main schema file to include new types
3. Run the code generation scripts to update the generated types
