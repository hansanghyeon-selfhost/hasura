# hasura

https://hasura.io/docs/2.0/getting-started/docker-simple/

healthcheck에서 헷갈렸던 부분이있었다.

"http://localhost:${DATA_CONNECTOR_AGENT_PORT:-8081}/api/v1/athena/health" 이렇게 테스트해서 실패했었다.

**healthcheck는 내부에서 실행되는 커맨드다**

## clerk

https://hasura.io/docs/2.0/auth/authentication/jwt/#running-with-jwt

```yaml
services:
  graphql-engine:
    environment:
      HASURA_GRAPHQL_ADMIN_SECRET: ${HASURA_GRAPHQL_ADMIN_SECRET:-myadminsecretkey}
      HASURA_GRAPHQL_JWT_SECRET: '{"jwk_url" : "https://<your-endpoint>/.well-known/jwks.json"}'
```

`HASURA_GRAPHQL_JWT_SECRET`를 설정하면 `HASURA_GRAPHQL_ADMIN_SECRET`는 필수로 설정해야 한다.
