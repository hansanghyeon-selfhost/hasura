# hasura

https://hasura.io/docs/2.0/getting-started/docker-simple/

healthcheck에서 헷갈렸던 부분이있었다.
"http://localhost:${DATA_CONNECTOR_AGENT_PORT:-8081}/api/v1/athena/health"
이렇게 테스트해서 실패했었다.
**healthcheck는 내부에서 실행되는 커맨드다**
