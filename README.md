# My App Kubernetes Deployment

Este repositorio contiene los manifiestos necesarios para desplegar una aplicación en un clúster de Kubernetes utilizando ArgoCD.

## Estructura del repositorio

```plaintext
/my-app-repo
├── k8s/
│   ├── deployment.yaml    # Manifiesto del Deployment
│   ├── service.yaml       # Manifiesto del Service
│   └── ingress.yaml       # Manifiesto opcional del Ingress
├── README.md              # Documentación del repositorio

Archivos incluidos
1. k8s/deployment.yaml
Define el Deployment para la aplicación, especificando el número de réplicas, la imagen del contenedor y el puerto.

2. k8s/service.yaml
Configura el Service para exponer la aplicación dentro del clúster de Kubernetes.

3. k8s/ingress.yaml (opcional)
Define un Ingress para exponer la aplicación al exterior del clúster. Este archivo es opcional y solo es necesario si tienes un controlador de Ingress configurado en tu clúster.

Requisitos previos
Antes de desplegar esta aplicación, asegúrate de tener:

Un clúster de Kubernetes funcionando (por ejemplo, Minikube).
ArgoCD instalado y configurado en tu clúster.
Un controlador de Ingress configurado si planeas usar el archivo ingress.yaml.
Instrucciones para el despliegue
Paso 1: Clonar el repositorio
Clona este repositorio en tu máquina local:

bash
Copiar
Editar
git clone https://github.com/tu-usuario/my-app-repo.git
cd my-app-repo
Paso 2: Configurar ArgoCD
Accede a la interfaz de ArgoCD.

Crea una nueva aplicación con los siguientes parámetros:

Repositorio Git: https://github.com/tu-usuario/my-app-repo.git
Ruta del manifiesto: k8s/
Clúster de destino: Selecciona tu clúster de Kubernetes.
Namespace: El namespace donde quieres desplegar la aplicación.
Sincroniza la aplicación desde la interfaz de ArgoCD.

Paso 3: Verifica el despliegue
Ejecuta los siguientes comandos para verificar que los recursos se hayan creado correctamente:

bash
Copiar
Editar
kubectl get deployments
kubectl get services
kubectl get ingress
Si todo está configurado correctamente, deberías ver tu aplicación en funcionamiento.

Personalización
Puedes personalizar los manifiestos según tus necesidades:

Cambia la imagen del contenedor en deployment.yaml para usar tu propia imagen Docker.
Modifica el tipo de servicio (NodePort, ClusterIP, LoadBalancer) en service.yaml.
Ajusta las reglas de Ingress en ingress.yaml para adaptarlas a tu dominio.
Recursos adicionales
Documentación de Kubernetes
Guía de ArgoCD
Minikube
