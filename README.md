# k8s-Helm-commands
Useful commands used on Internal bench DevOps projects

wire,
ART,
Soc,
HOF

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

> kubectl get deploy -n staging (get deployments in staging namespace)

> kubectl describe deploy staging-wire-bot -n staging (describe deployment)

> kubectl get deploy staging-wire-bot -n staging -o yaml (view deployment yaml file)

> kubectl set image deployment/staging-wire-bot bot=gcr.io/bench-projects/wire-bot:9b729c5 -n staging (update deployment with new image)

> git rev-parse HEAD (get repo commit head)

> git rev-parse --short HEAD (get short commit head)

> docker tag gcr.io/bench-projects/wire-bot gcr.io/bench-projects/wire-bot:$(git rev-parse --short HEAD) (tagging image with commit head)

> docker push gcr.io/bench-projects/wire-bot:$(git rev-parse --short HEAD) (push image)

> alias (new)=(real-command)

> make init (intialize helm against a cluster)

> make install --- (install helm chart in a k8s cluster)

> make upgrade -------- (update helm chart with changes for a new release)

> make encrypt ----- (encrypt chart secrets file)

> helm delete --purge staging-art (delete helm release called staging-art)

> kubectl config current-context (check current k8s cluster context)

> make upgrade ingress staging (upgarde ingress after modification)

> kubectl logs pod/staging-wire-bot-8795944c7-5k2l7 -n staging (logs command)

> to-dos

> configure CI pipeline for wire api

> configure CI pipeline for wire-frontend

> do surveys

> review bash-utils-scripts
