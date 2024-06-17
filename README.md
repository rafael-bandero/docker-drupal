## Drupal with Docker
Basic Docker environment to execute Drupal in localhost with SSL enabled

### TODO

- Automate Cert generation and remove nginx/certs from docker-compose.yml:

```bash
openssl genpkey -algorithm RSA -out nginx/certs/localhost.key
```

```bash
openssl req -new -key nginx/certs/localhost.key -out nginx/certs/localhost.csr
```

```bash
openssl x509 -req -days 365 -in nginx/certs/localhost.csr -signkey nginx/certs/localhost.key -out nginx/certs/localhost.crt
```

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
