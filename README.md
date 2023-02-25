## Simple todo app with K8s cluster, Docker Compose and Jenkins
- Containerization of Node.js Project using Docker
- Deployment application with Docker compose, Kubernetes
- CI/CD Pipeline using Jenkins

---------- With docker compose ----------
```bash
touch .env
vi .env 
```
MYSQLDB_USER=root

MYSQLDB_ROOT_PASSWORD=123456

MYSQLDB_DATABASE=user
```bash
docker compose up
```

<!-- ---------- With Swarn cluster -----------
```bash
cd docker/
```
```bash
echo 'mypassword' | docker secret create todo-app-MYSQL_PASSWORD -
docker stack deploy --compose-file swarm-deploy.yml
``` -->

---------- With Kubernetes cluster ----------
```bash
cd k8s/
kubectl apply -f secret-volume.yaml
kubectl apply -f db.yaml
kubectl apply -f backend.yaml
```
<!-- ### How I deploy it
* <a href="https://github.com/bao-nguyen-khac/devops-setup.git" target="_blank">Reference</a> -->

### Link demo: <a href="https://todo-app.baonk.site" target="_blank">todo-app.baonk.site</a>
