# Paso a paso del despliegue

### 0. Namespace
* microk8s kubectl apply -f namespace.yaml


### 1. Catalogo

### 1.1 Base de datos:
* microk8s kubectl apply -f mysql-catalog.yaml

* microk8s kubectl apply -f catalog-backend.yaml

### Desde un navegador 
* http://<Node-IP>:30300/docs


### 2. Reviews

### 2.1 Base de datos:
* microk8s kubectl apply -f mongo-reviews.yaml

* microk8s kubectl apply -f reviews-backend.yaml

### Desde un navegador 
* http://<Node-IP>:30200/docs


### 3. Store

### 3.1 Base de datos:
* microk8s kubectl apply -f mysql-store.yaml

* microk8s kubectl apply -f store-backend.yaml

### Desde un navegador 
* http://<Node-IP>:30400/docs

## Para la prueba en postman:
### Catalogo
* http://<Node-IP>:30300/api/getlibros
* http://<Node-IP>:30300/api/libro (se le pasa un raw Json)
* http://<Node-IP>:30300/api/libro (se le pasa un raw Json)
* http://<Node-IP>:30300/api/deletelibro?ISBN=11111111122233

### Reviews
* http://<Node-IP>:30200/reviews
* http://<Node-IP>:30200/addreviews?usuario=User&isbn=11111111122233&estrellas=4&comentario=muy bueno la verdad
* http://<Node-IP>:30200/deletereviews?usuario=User&isbn=11111111122233

### Store
* http://<Node-IP>:30400/api/getcart?usuario=User
* http://<Node-IP>:30400/api/addcart?usuario=User&isbn=22222222&cantidad=1
* http://<Node-IP>:30400/api/buycart?usuario=User
* http://<Node-IP>:30400/api/deletecart?isbn=22222222&usuario=User
