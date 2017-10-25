# Interesting points

- Have technical documentation generated off the graphql schema
- Expose a single GraphQL gateway which you can expose via GraphiQL so users can play around with the Data Fabric
- Dont let runtime define schema definition but let it be done at compile time
( goes back to generic columns in the graphql schema or the concept of the "generic" "Object" )
- Instrumenting the calls on each field so you know exactly whats being queried
- Apollo Engine has a proxy that caches the data based on a ttl ( read on it ) and supports distributed caching or a default cache
- Optimistic UI
- Subscriptions and Live Queries
- 1MB github json message payload limit
- Static analysis of query to find out what the cost of the query is because rate limiting is much harder in graphql than in rest . Done by github ( done at the onset of the query). To give back an estimation of the work that will be needed to be done on the server side ( request budget )
- Really gotta use data loader to retrieve responses otherwise things go awry v quickly
- Create middleware like gramps 
