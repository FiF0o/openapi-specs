# POC

## Description
This package is a proof of concept to create modular openapi specs from design to deployment steps.
_Node 12+ is required._


## Workflow & Scripts
Assumption: development is design driven, technical design is defined then implemented. open api specification drives the development and acts as a single source of truth


```sh

# 1. Specification is defined by the team using an openapi3.x using a modular approach
# Something schema as $ref from main.yml
./openapi/main.yml


# 2. Specifications are received then implemented by the development team.
# Validate specs
npm run openapi:lint

# 3. Schemas from the openapi specs are derived and typescript interfaces created
# ./openapi/components/something.ts. something.yml > something.ts
npm run openapi:generate:interfaces


# 4. Deployment is done with IaC. One single file to be consumed for deployment as megaspec.yml
# ./dist/megaspec.yml
openapi:create
```

