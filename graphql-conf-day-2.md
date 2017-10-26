# Day 2

## Apollo ( @stubailo )
- GraphQL caching
  - DOnt cache inside the server. Do it somewhere in the middle of the front end and the backend
  - GraphQL gateway
    - ( GraphQL client ) ------ [ GraphQL Gateway ] ------ ( GraphQL server )
      - Infrastructure related things like proxying
      - Tracing
        - Spec - Apollo Tracing
      - Errors
      - Caching
        - Fine grained cache control
- Schema stitching is the way to go for disparate sources of data to expose a unified schema for the client to use

## Twitch ( @tonyghita )

- Cursor pagination is implicitly understood by graphql
- Authorization pushed to the services not the gateway
- Dan Schafer talk on Authorization
- invest time in building out a styleguide for the schema. Add linters for this so you dont have to humanly monitor each step of the schema development . Just run the linter
- Generate code for resolvers/schema
- GRPC, Protobufs with codegen to generate end to end code generation from an API standpoint

## Formidable ( @ebaerbaerbaer )

- Persisted/static queries
  - Queries are stored where both client and server can access
    - Network caching
    - Order of magnitude faster
    - Both talk via an "id" of the query and not the actual query itself
- Operation steps in query execution     
  - GetOperation    
  - CooerceVariableValues
  - ExecutionQuery
    - ExecutionSelctionSet
      - ExecuteField
        - CooerceArgumentValues
        - ResolveFieldValue
        - CompleteValue
- Javascript being single threaded at its core doesnt let parallelizing the parsing and validation of queries parallelized

## Apollo

- Normalized Caching

## Khan Academy

- Track 500 errors on a dashboard
- Make errors actionable by giving trace and lines of code where error happened etc

# Auth0 -( @ryanchenkie )

- Auth using
  - Wrapping resolvers
  - Custom directives
    - Used for authorizing specific fields
- Using JWT ( jwt.io) for authentication
- FInd the bitly link for the slides for examples of directives and wrapped resolvers

# KLM
- GraphQL IDE plugin ( VSCode and webstorm. possibly atom )
- Use UBC ( Unique Business component ) as individual microservices
- They dont front the services with a middle ware to handle incoming requests that would treat all the services as one big schema.
- Using this.apollo.watchQuery and this.apollo.mutate

# Lightning talks

## Dev tools for Dev Ex

graphql/named-operations
graphql/required-fields

If youre making breaking schema changes, run it against product code ( in eslint ) to figure out what broke

Use Apollo code gen to generate flow/ts code

# Twitter

Instead of tracking % of requests served ( 99.99% ) they track number of exceptions per query and based on that see how reliable the system is
