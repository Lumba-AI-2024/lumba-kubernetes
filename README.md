### Run the following **IN ORDER**
``` bash
kubectl create secret generic lumba-secret --from-env-file=.env
kubectl apply -f lumba-api-config.yaml
kubectl apply -f lumba-model-config.yaml
kubectl apply -f lumba-api.yaml
kubectl apply -f lumba-model.yaml
kubectl apply -f lumba-celery-worker.yaml
```