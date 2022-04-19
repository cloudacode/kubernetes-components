# KEDA 

## Install
https://keda.sh/docs/2.6/deploy/

```bash
kubectl create ns keda
helm upgrade --install keda kedacore/keda -n keda
```

## Deploy sample app

[hello-world](../hello-world/)

## Config ScaledObject

```bash
#for path /
kubectl apply -f hpa-nginx-request-total.yaml 

#for path /v2
kubectl apply -f hpa-v2-nginx-request-total.yaml 
```