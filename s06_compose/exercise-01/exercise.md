## Create a docker-compose to deoloy a Drupal application using PostgreSQL as DB.
- Drupal is exposed at port 8080

- Setup password for PostgreSQL DB
- Create a network for both container
- Persist data of both container by using Volume


## Provision cms system with docker-compose command

```bash
docker-compose --env-file .env_qa up -d
```


## Decommission 
```bash
docker-compose --env-file .env_qa down
```