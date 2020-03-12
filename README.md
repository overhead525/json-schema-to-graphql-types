# JSON Schema to GraphQL Types Converter

[![Greenkeeper badge](https://badges.greenkeeper.io/lifeomic/json-schema-to-graphql-types.svg)](https://greenkeeper.io/)
[![Build Status](https://travis-ci.org/lifeomic/json-schema-to-graphql-types.svg?branch=master)](https://travis-ci.org/lifeomic/json-schema-to-graphql-types)
[![Coverage Status](https://coveralls.io/repos/github/lifeomic/json-schema-to-graphql-types/badge.svg?branch=master)](https://coveralls.io/github/lifeomic/json-schema-to-graphql-types?branch=master)

This tools will convert a directory of JSON Schemas into set of GraphQL types.
To use it, do the following:

    npm install -g @lifeomic/json-schema-to-graphql-types
    convert-json-schemas-to-graphql-types <some-dir-with-json-schemas>

When that is run, the tool will output a list of GraphQL types that match the
types in the JSON schemas. After generating the types, you'll need to create
Query and Mutation types to complete your schema and then add resolvers as
needed.

## Example JSON Schema

A valid JSON Schema has the following format:

json-schemas/schema-1

```
{
  "$id": "DummyData",
  "type": "object",
  "properties": {
    "attribute": {
      "type": "string"
    }
  }
}
```

json-schemas/schema-2

```
[
  {
    "$id": "schema1",
    "type": "object",
    "properties": {
      "attribute": {
        "type": "string"
      }
    }
  },
  {
    "$id": "schema2",
    "type": "object",
    "properties": {
      "attribute": {
        "type": "string"
      }
    }
  }
]
```

1. `$id` does something
2. `type` does something
3. `properties` does something

## Example Usage

    convert-json-schemas-to-graphql-types json-schemas

## Example Output

### Schema 1

```
type DummyData {
  attribute: String
}

input DummyDataIn {
  attribute: String
}

type Mutation {
  DummyData(input: DummyDataIn): String
  Schema1(input: Schema1In): String
  Schema2(input: Schema2In): String
}
```

### Schema 2

```
type Schema1 {
  attribute: String
}

input Schema1In {
  attribute: String
}

type Schema2 {
  attribute: String
}

input Schema2In {
  attribute: String
}
```
