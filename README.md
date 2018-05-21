# k8s-Helm-commands
Useful commands used on Internal bench DevOps projects

>Install helm

>Install kubectl & minikube
> minikube start (to communicate to remote cluster)
### make init
### gcloud auth login (authenticate to cluster)
### gcloud auth application-default login (login)
### make install "project" "environment) (e.g. make install wire staging) to install project chart
### helm ls (to list charts)
### helm status staging-wire (check status)
### gcloud container clusters get-credentials bench-staging --zone us-central1-a --project bench-projects (change context)
### kubectl get ns (get namespace)
### kubectl get pods -n staging (get pods under namespace staging)

