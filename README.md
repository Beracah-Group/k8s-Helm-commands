# k8s-Helm-commands
Useful commands used on Internal bench DevOps projects

>Install helm

>Install kubectl & minikube

> minikube start (to communicate to remote cluster)

> make init

> gcloud auth login (authenticate to cluster)

> gcloud auth application-default login (login)

> helm plugin install https://github.com/futuresimple/helm-secrets (install secret plugin)

> make install "project" "environment) (e.g. make install wire staging) to install project chart

> helm ls (to list charts)

> helm status staging-wire (check status)

> gcloud container clusters get-credentials bench-staging --zone us-central1-a --project bench-projects (change context)

> kubectl get ns (get namespace)

> kubectl get pods -n staging (get pods under namespace staging)

> kubectl get deployment -n staging (get deployments in staging namespace)

> kubectl describe deployment/staging-wire-backend -n staging (describe a single deployment in staging namespace)

> kubectl port-forward staging-wire-backend-5f8fc589f8-2xswj 3000:3000 -n staging (port forwaring of a pod in the staging namespace)

> make edit art staging (access wire staging secrets)

> init (intialize helm against a cluster)

> install (install helm chart in a k8s cluster)

> upgrade (update helm chart with changes for a new release)

> encrypt (encrypt chart secrets file)

> helm delete --purge staging-art (delete helm release called staging-art)

> kubectl config current-context (check current k8s cluster context)
