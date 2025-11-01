1. Запуск minikube:
```bash
minikube start --driver=docker
```

2. Активация metrics-server и ingress:
```bash
minikube addons enable metrics-server 
minikube addons enable ingress
```

3. Создайте namespace, deployment, service:
```bash
kubectl apply -f test-app.yaml
```

4. Применение манифеста HPA
```bash
kubectl apply -f hpa.yaml
kubectl get hpa 
```

5. запуск  locust

```bash
python3 -m locust
```

http://0.0.0.0:8089/

6. Запуск dashboard 

```bash
minikube dashboard 
```

7. Удалить namespace и hpa
```bash
kubectl delete namespace test
kubectl delete hpa test-app-hpa
```