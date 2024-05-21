# Kubernetes Based Deployment of Lumba-AI AutoML Stacks


### 1. Create a '.env' file on root
```
ENV=
DEBUG=
DJANGO_SECRET_KEY=
PSQL_DB_NAME=
PSQL_USER=
PSQL_PASSWORD=
PSQL_HOST=

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_S3_ENDPOINT_URL=

REDIS_ENDPOINT_URL=
```

### 2. Run the following **IN ORDER**
``` bash
kubectl create secret generic lumba-secret --from-env-file=.env
kubectl apply -f lumba-api-config.yaml
kubectl apply -f lumba-model-config.yaml
kubectl apply -f lumba-api.yaml
kubectl apply -f lumba-model.yaml
kubectl apply -f lumba-celery-worker.yaml
```

### 3. Expose the port to lumba-api
```bash
kubectl port-forward service/lumba-api-service 8000:80
```
