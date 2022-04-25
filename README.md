# About
A simple kubernetes cluste for learning, running on minikube

# Notes

#### Create a new / start up existing minikube cluster
`minikube start`

#### Shut down minikube when done testing to save resources
`minikube stop`

#### Enable docker registry and ingress controller for minikube
`minikube addons enable registry`

`minikube addons enable ingress`

#### Configure terminal to use the docker daemon/repo inside minikube (more reading: https://minikube.sigs.k8s.io/docs/handbook/pushing/)
`eval $(minikube docker-env)`

#### Build docker image
`docker build . -t wachmann.dev/http-test-service`

#### Make sure kubectl is using the minikube context for commands
`kubectl config use-context minikube`

#### Deploy kubnernetes resources to minikube
`kubectl apply -f ./k8s`

#### Get the ip address of minikube
`minikube ip`

#### the local /etc/hosts file should have been edited to point http-test-service.info to the minikube ip
`192.168.64.3 http-test-service.info`

#### Verify that the ingress works and we can hit the golang service running in minikube
`curl http-test-service.info`