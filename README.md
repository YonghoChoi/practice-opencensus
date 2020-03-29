# practice-opencensus

프로메테우스에 아래 설정 추가

```
... 생략 ...
scrape_configs:
  ... 생략 ...
  - job_name: 'practice'
    scrape_interval: 10s
    static_configs:
      - targets: ['docker.for.win.localhost:8080']
```



지표 확인을 위한 부하 발생

```
docker run --rm jordi/ab -k -c 10 -n 5000 http://docker.for.win.localhost:8080/list
```