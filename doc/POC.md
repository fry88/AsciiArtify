# Installing and Configuring Command Access to the ArgoCD Graphical Interface in Kubernetes Cluster k3d

## Prerequisites

- k3d installed on your local machine
- kubectl installed on your local machine

## Installation

1. Create a k3d cluster by running the following command:

   ```
   k3d cluster create {name of your cluster}
   ```

2. Install the ArgoCD by running the following command:

   ```
    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

   ```

3. Wait for the ArgoCD deployment to complete.

4. To access the ArgoCD web interface, run the following command to expose the service:

   ```
   kubectl port-forward svc/argocd-server -n argocd 8088:443
   ```

5. To retrieve the password, run the next command
   ```
   argoPass=$(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d)
   echo $argoPass
   ```
6. Open a web browser and navigate to `https://localhost:8080`. You should now be able to access the ArgoCD graphical interface.

7. For access use the password from step 5 to log in and name admin


![Screen-Recording-2023-05-28-at-00 07 00](https://github.com/fry88/AsciiArtify/assets/75542876/06ddb32b-039c-4306-a7b3-adbea6cc48ff)
