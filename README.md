![Scheme](/scheme.png)

# Application monitoring with Traefik, Prometheus, Grafana, and Docker Compose for beginners

This is my vision of a simple monitoring infrastructure. Read more in the [article](https://medium.com/@evgeniyfirstov/application-monitoring-with-traefik-prometheus-grafana-and-docker-compose-for-beginners-2fe25d1b60a8).

Simple startup:

```
docker-compose --env-file .env.dev -f infrastructure.yml up -d
docker-compose --env-file .env.dev -f example-backend.yml up -d
```

## Note

Login credentials are:

- User: 'admin'
- Password: 'admin'
