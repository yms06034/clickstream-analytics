# clickstream-analytics(java)
JAVA를 사용해 Log Data를 만들어 실시간 클릭 데이터를 데시보드로 넘기는 Pipeline 프로젝트 입니다.

## Description
본 프로젝트는 Kafka와 Flink를 활용할 수 있는 방안을 생각해 진행한 프로젝트 입니다.

실제 실무에서 사용할 만한 실시간 데이터를 어떻게 처리하는지에 대해 대략적인 프로세스를 익히는 데 도움이 많이 되었습니다.

## Environment
- Docker
- Kafka
- Flink
- MySQL
- Grafana

## Files
- [log-generator project](./log-generator/)
- [clickstream-analyzer project](./clickstream-analyzer/)

## Grafana Dashboard 
- New Dashboard
- New Panel
  - Data source : MySQL
  - Query
  ```sql
  SELECT
    unix_timestamp(ts) AS "time",
    active_session
  FROM stats
  ORDER BY ts
  ```
    ```sql
  SELECT
    unix_timestamp(ts) AS "time",
    ads_per_second
  FROM stats
  ORDER BY ts
  ```
  ```sql
  SELECT
    unix_timestamp(ts) AS "time",
    request_per_second
  FROM stats
  ORDER BY ts
  ```
  ```sql
  SELECT
    unix_timestamp(ts) AS "time",
    error_per_second
  FROM stats
  ORDER BY ts
  ```