
# Apuntes Kubernetes-k8s



## Namespaces (Ambientes)
Kubernetes soporta múltiples clústeres virtuales respaldados por el mismo clúster físico. Estos clústeres virtuales se denominan espacios de nombres (namespaces).

### Mostrar los Namespaces
kubectl get namespaces

### Crear un NameSpace
kubectl apply -f .\namespace.yml

### Borrar un NameSpace
kubectl delete -f .\namespace.yml



## Pod (Contenedor)
Un Pod (como en una vaina de ballenas o vaina de guisantes) es un grupo de uno o más contenedores (como contenedores Docker), con almacenamiento/red compartidos, y unas especificaciones de cómo ejecutar los contenedores. Los contenidos de un Pod son siempre coubicados, coprogramados y ejecutados en un contexto compartido. Un Pod modela un "host lógico" específico de la aplicación: contiene uno o más contenedores de aplicaciones relativamente entrelazados. Antes de la llegada de los contenedores, ejecutarse en la misma máquina física o virtual significaba ser ejecutado en el mismo host lógico.

### Cuando usarlo?
Es muy similar a un contenedor de Docker, se utiliza cuando solo se necesita una instancia y no se ocupa un escalado horizontal

### Mostar pods
kubectl get pods

### Crear un pod
kubectl apply -f .\pod.yml

### Entrar a un pod
kubectl exec -it wildfly -- /bin/bash

### Ver logs a un pod
kubectl logs -f wildfly

### Delete un pod
kubectl delete -f .\pod.yml



## Deployment
Es similar un orquestador. Un controlador de Deployment proporciona actualizaciones declarativas para los Pods y los ReplicaSets.

Cuando describes el estado deseado en un objeto Deployment, el controlador del Deployment se encarga de cambiar el estado actual al estado deseado de forma controlada. Puedes definir Deployments para crear nuevos ReplicaSets, o eliminar Deployments existentes y adoptar todos sus recursos con nuevos Deployments.

### Crear un deployment
kubectl apply -f .\deployment.yml

### Obtener un deployment
kubectl get deployments

### Eliminar un deployment
kubectl delete -f .\deployment.yml


## Service
Un Service, servicio en castellano, es el objeto de la API de Kubernetes que describe cómo se accede a las aplicaciones, tal como un conjunto de Pods, y que puede describir puertos y balanceadores de carga.
Con Kubernetes no necesitas modificar tu aplicación para que utilice un mecanismo de descubrimiento de servicios desconocido. Kubernetes le otorga a sus Pods su propia dirección IP y un nombre DNS para un conjunto de Pods, y puede balancear la carga entre ellos.
Expone un conjunto de pods de manera unificada, como si fuera un DNS

## Crear un servicio
En este caso un servicio serira para ayudar a comunicar dos pods de diferentes despliegues




## Ingress

Se dedida a dar conectividad desde Internet por ejemplo hacia un services de un cluster

Un objeto API que gestiona el acceso externo a los servicios en un clúster, normalmente HTTP.
Ingress puede proporcionar equilibrio de carga, terminación SSL y alojamiento virtual basado en nombres




