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
