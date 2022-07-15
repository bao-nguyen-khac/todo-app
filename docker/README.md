---------- On docker compose ----------
```bash
touch .env
vi .env 
```
MYSQLDB_USER=root

MYSQLDB_ROOT_PASSWORD=123456

MYSQLDB_DATABASE=user
```bash
docker-compose up
```
---------- On Swarn cluster -----------
```bash
cd docker/
```
```bash
echo 'mypassword' | docker secret create todo-app-MYSQL_PASSWORD -
docker stack deploy --compose-file swarm-deploy.yml
```