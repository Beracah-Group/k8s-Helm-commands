## Docker kubernetes and Helm commands used on DevOps projects (Former Andela Internal Products)


## Projects (deprecated / nolonger supported / non existent)

Wire
ART
Soc
HOF
Meals
andela socials
Andela Eats
Andela socials
Engagement Support Automation
Travel readiness
Meal card


> https://docs.helm.sh/using_helm/#quickstart

> First Install helm (based on old version that required tiller)

> Install kubectl & minikube

> minikube start (to communicate to remote cluster)

> run `make init` (all abstraction of commands done in makefile)

> gcloud auth login (authenticate to cluster) (this too changed regarding using GCR)

> gcloud auth application-default login (login)

> helm plugin install https://github.com/futuresimple/helm-secrets (install secret plugin)

> make install "project" "environment) (e.g. make install wire staging) to install project chart

> helm ls (to list charts)

> helm status staging-wire (check status)

> gcloud container clusters get-credentials bench-staging --zone us-central1-a --project bench-projects (change context)

> kubectl get ns (get namespace)

> kubectl exec -it staging-wire-backend-56b84b5d8b-kc4w6 -n staging /bin/bash (exec commands in a pod)

> kubectl port-forward staging-hof-backend-5f9cfcbfb6-6n4k5 8080:8080 -n staging (port forward)

> kubectl get svc (get service)

> kubectl get pods -n staging (get pods under namespace staging)

> kubectl get deployment -n staging (get deployments in staging namespace)

> kubectl describe deployment/staging-wire-backend -n staging (describe a single deployment in staging namespace)

> kubectl port-forward staging-wire-backend-5f8fc589f8-2xswj 3000:3000 -n staging (port forwaring of a pod in the staging namespace)

> make edit art -n prod (access wire prod secrets)

> kubectl get deploy -n staging (get deployments in staging namespace)

> kubectl describe deploy staging-wire-bot -n staging (describe deployment)

> kubectl get deploy staging-wire-bot -n staging -o yaml (view deployment yaml file)

> kubectl set image deployment/staging-wire-bot bot=gcr.io/bench-projects/wire-bot:9b729c5 -n staging (update deployment with new image)

> docker build -t gcr.io/bench-projects/art2-backend .

> git rev-parse HEAD (get repo commit head)

> git rev-parse --short HEAD (get short commit head)

> docker tag gcr.io/bench-projects/wire-bot gcr.io/bench-projects/wire-bot:$(git rev-parse --short HEAD) (tagging image with commit head)

> docker push gcr.io/bench-projects/wire-bot:$(git rev-parse --short HEAD) (push image)

> docker build -t gcr.io/bench-projects/art2-backend .

> docker tag gcr.io/bench-projects/art2-backend gcr.io/bench-projects/art2-back
end:$(git rev-parse --short HEAD)

> docker push gcr.io/bench-projects/art2-backend:$(git rev-parse --short HEAD)

> alias (new)=(real-command)

> make init (intialize helm against a cluster)

> make install --- (install helm chart in a k8s cluster)

> make upgrade -------- (update helm chart with changes for a new release)

> make encrypt ----- (encrypt chart secrets file)

> helm delete --purge staging-art (delete helm release called staging-art)

> kubectl config current-context (check current k8s cluster context)

> make upgrade ingress staging (upgarde ingress after modification)

> kubectl logs pod/staging-wire-bot-8795944c7-5k2l7 -n staging (logs command)

> kubectl get svc

> kubectl get endpoints {service_name}

> docker run --publish 8080:8080 -it gcr.io/bench-projects/art3-backend:staging
-ea6c86d  (map local port to container port)

> docker run -it gcr.io/bench-projects/art3-backend:staging-ea6c86d  (run docker image in gcr.io)

>  source .env  (source env variables in .env home folder)

> sudo easy_install pip  (install pip)

> curl ifconfig.co  (get ip address)

> curl ifconfig.co  (get ip address)

> nslookup "domain" (check ip address domain is mapped to)

HELM SECRETS LINKS

> https://github.com/futuresimple/helm-secrets

https://stackoverflow.com/questions/42101808/ingress-gives-502-error?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa stackoverflow answer solving 200 redirect to 302 because of autoresolve thus causing 502

GKE INGRESS Links

> GKE Ingress controller

source code and tutorial
- https://github.com/kubernetes/charts/tree/master/stable/nginx-ingress
- https://github.com/GoogleCloudPlatform/community/blob/master/tutorials/nginx-ingress-gke/ingress-resource.yaml
- https://cloud.google.com/community/tutorials/nginx-ingress-gke
- https://github.com/kubernetes/ingress-gce/blob/master/README.md#frontend-https

- https://github.com/kubernetes/helm/issues/3055
- https://docs.bitnami.com/kubernetes/how-to/secure-kubernetes-services-with-ingress-tls-letsencrypt/

GKE JENKINS/k8s Links

- https://cloud.google.com/solutions/jenkins-on-kubernetes-engine-tutorial

GKE MONITORING

- https://cloud.google.com/kubernetes-engine/docs/how-to/monitoring
- https://kubernetes.io/docs/tasks/debug-application-cluster/logging-stackdriver/#deploying-to-an-existing-cluster
- https://cloud.google.com/kubernetes-engine/docs/how-to/logging
