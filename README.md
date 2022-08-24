# Simple todo app with K8s cluster, Docker swarm and Jenkins

---------- With docker compose ----------
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

---------- With Swarn cluster -----------
```bash
cd docker/
```
```bash
echo 'mypassword' | docker secret create todo-app-MYSQL_PASSWORD -
docker stack deploy --compose-file swarm-deploy.yml
```

---------- With Kubernetes cluster ----------
```bash
cd k8s/
kubectl apply -f secret-volume.yaml
kubectl apply -f db.yaml
kubectl apply -f backend.yaml
```