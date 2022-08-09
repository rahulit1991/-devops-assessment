# Guide to run assessment

## Prerequisites

Install k3d cluster with PodSecurityPolicy with following command :
- docker
- k3d cluster
- helm 

Create k3d cluster with following command

```sh
make cluster
```

## Install helm charts: Jenkins, ingress-nginx, Promethous

```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
kubectl create ns monitoring

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus-chart prometheus-community/prometheus -n monitoring

helm repo add jenkins https://charts.jenkins.io
helm repo update
helm install jenkins-ci jenkins/jenkins


helm install ingress-chart ingress-nginx/ingress-nginx
```

## Deploy application by running following manifest files

```sh
kubectl apply -f deployment.yaml
kubectl apply -f ingress.yaml
```    

## Deploy application with following manifest files: 

```sh
kubectl apply -f deployment.yaml
kubectl apply -f ingress.yaml
```    

## Check your application over browser with IP or domain

- In my case, you check application on http://api.opstudio.cloud/health and 
- check jenkins running on http://jenkins.opstudio.cloud/

