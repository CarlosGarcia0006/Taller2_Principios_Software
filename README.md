# Paso a paso del despliegue

# 0. Namespace
* microk8s kubectl apply -f namespace.yaml


# 1. Catalogo

# 1.1 Base de datos:
* microk8s kubectl apply -f mysql-catalog.yaml

* microk8s kubectl apply -f catalog-backend.yaml

# Desde un navegador 
* http://<Node-IP>:30300/docs


# 2. Reviews

# 2.1 Base de datos:
* microk8s kubectl apply -f mongo-reviews.yaml

* microk8s kubectl apply -f reviews-backend.yaml

# Desde un navegador 
* http://<Node-IP>:30200/docs


# 3. Store

# 3.1 Base de datos:
* microk8s kubectl apply -f mysql-store.yaml

* microk8s kubectl apply -f store-backend.yaml

# Desde un navegador 
* http://<Node-IP>:30400/docs
