# Kibana Docker Env

## Usage

### 解析用ログファイルを配置

/embulk/works/log 下に配置。

### インポート

```bash
docker-compose up
docker-compose exec embulk bash -c "embulk run config.yml.liquid"
```

Kibana:

[http://localhost:5601/](http://localhost:5601/)