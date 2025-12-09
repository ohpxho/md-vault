# GraphQL notes - Oct. 30, 2025

## What us GraphQL

- An open source query language for API
- Server side runtime for executing quieries using a type system defined in the data

## Type System

### Object types

- The most basic component of GrapQL types
- Represents an object that contains fields that holds a certain or a set of value

```
type Character {
    name: String!
    appearsIn: [Episode!]!
}
```

### Scalar Types

- Set of default scalar types:
  1. Int (32-bist signed)
  2. Float (signed double precision)
  3. String (utf-8 character sequence)
  4. Boolean
  5. ID (unique identifier, serialized, a string)

### Custom Scalar Type

- use `scalar` keyword to define a scalar

### Enum Types

- an enumeration
- a special kind of scalar that is restricted to a particular set of allowed values

```
enum Episode {
  NEWHOPE
  EMPIRE
  JEDI
}
```

### Type Modifiers

- By defualt types are assumed as **singular** and **nullable**
- Use `!` to declare that the type is not nullable
- Use `[]` to declare that the type is a list

```
GraphQL supports abstract types
```

### Interface Types

- An abstract type that defines a shared set of fields that multiple object types can implement
- Every concrete type that implements the interface must include all the properties in the interface to the properties declared in the concrete type

```
interface Character {
  id: ID!
  name: String!
  friends: [Character]
  appearsIn: [Episode]!
}

type Human implements Character {
  id: ID!
  name: String!
  friends: [Character]
  appearsIn: [Episode]!
  starships: [Starship]
  totalCredits: Int
}
```

### Union Types

- An abstract type that groups multiple concrete type objects where each type can be an output of the union type object
- Members of union types should all be concrete

```
union SearchResult = Human | Droid | Starship
```

### Input Type Objects

- Refers to objects that are passed as arguments
- This is particularly used in Mutation operation where you might pass in a whole object to be created
- You declare thse type with the use of `input` keyword
- Can refer to other Input Object Types
- Cannot have arguments on their fields

```
input ReviewInput {
  stars: Int!
  commentary: String
}

type Mutation {
  createReview(episode: Episode, review: ReviewInput!): Review
}
```

### Directives

- An annotation that changes how Graphql executes a query or interprets a schema
- Use `@` to define a directive
- This allows dynamic queries, where you can change how data will be fetch for some data based by the variable set in the argument (refer to example below to see)
- Built-in directives:

  - `@include` - include a field if the argument is true
  - `@skip` - skips a field of the argument is true

  ```
  query GetUser($skipEmail: Boolean!) {
        user(id: "1") {
            name
            email @skip(if: $skipEmail)
        }
  }

  if the $skipEmail is true, the result wont contain any emails
  ```

### Operation type

- These types describes the type of operation to perform by gql
- There are 3 types of operation:
  - `query`
  - `mutation`
  - `subscription`

## Queries

### Arguments
