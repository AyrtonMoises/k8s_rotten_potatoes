# Rotten-potatoes


### Instalando utilizando com MINIKUBE
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

### Instalando KUBECTL
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client
```

### Configurando Minikube
```
minikube start --driver=docker
minikube config set driver docker # define como padrão para proximas vezes
sudo usermod -aG docker $USER && newgrp docker

minikube start
minikube dashboard # abre no navegador a UI
```

### Aplica configuração
```
kubectl apply -f k8s/deployment.yaml
```

### Habilita acesso na porta 8080
```
kubectl port-forward service/web-service 8080:80
```
