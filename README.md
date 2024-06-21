## Drupal with Docker
Basic Docker environment to execute Drupal in localhost with SSL enabled

### Install and Run

- Create a `.env` file using `.env-example` as a model

- Start containers:

```bash
docker-compose up -d
```

- Get db container IP ( **## TODO: automate this** ):

```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' db
```

- Access https://localhost and finish standard Drupal installation.
