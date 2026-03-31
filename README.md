# Local Observability Stack

Локальний стек спостережуваності для моніторингу метрик і збору логів веб-сервісу на базі Nginx.

# Склад стеку

- Docker Compose
- Nginx
- Nginx Prometheus Exporter
- Node Exporter
- Prometheus
- Loki
- Promtail
- Grafana

# Структура проєкту

.
- docker-compose.yml
- nginx/
- prometheus/
- loki/
- promtail/
- grafana/
- README.md

Запуск - docker compose up -d

# Доступні URL
- Nginx: http://localhost:8080
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000
- Loki readiness: http://localhost:3100/ready
- Node Exporter: http://localhost:9100/metrics
- Nginx Exporter: http://localhost:9113/metrics

# Дані для входу в Grafana
login: admin
password: admin
# Що відображає dashboard
- Nginx active connections
- Nginx requests per second
- CPU usage
- RAM usage
- Nginx logs stream
- Перевірка логів

# Щоб згенерувати логи:

- curl http://localhost:8080
- curl http://localhost:8080/stub_status


# Збереження даних

Використовуються Docker Volumes:

- prometheus_data
- loki_data
- grafana_data
