\# Kubernetes Helm Demo



\## Project Overview



This project demonstrates deploying an NGINX application to a local Kubernetes cluster using Helm charts and Docker Desktop Kubernetes.



\## Technologies



\* Kubernetes

\* Helm

\* Docker Desktop

\* NGINX



\## Helm Chart Structure



\* `Chart.yaml` — Chart metadata

\* `values.yaml` — Application configuration

\* `templates/` — Kubernetes resource templates



\## Prerequisites



\* Docker Desktop with Kubernetes enabled

\* kubectl

\* Helm



\## Deployment Steps



Validate the Helm chart:



```powershell

helm lint .

```



Install the application:



```powershell

helm install myapp . --namespace dev --create-namespace

```



Verify the deployment:



```powershell

helm list -n dev

kubectl get pods -n dev

kubectl get deployments -n dev

kubectl get services -n dev

```



Access the application locally:



```powershell

kubectl port-forward service/myapp 8080:80 -n dev

```



Open `http://localhost:8080` in your browser.



\## Result



The NGINX application was deployed successfully to the local Kubernetes cluster. The Pod reached `Running` status with `1/1` containers ready, and the NGINX welcome page was accessible through port forwarding.



