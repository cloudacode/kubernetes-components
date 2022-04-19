# How ingress works with multiple backend

Create the following sample application to test ingress that has multiple backend services.

## Architecture

```
   hello.p.cloudacode.com     +---+
                           +-->pod|
                           |  +---+
                           |
 +---+   /*    +---------+ |  +---+
 |   +--------->service-1+-+-->pod|
 | L |         +---------+    +---+
 |   |
 | B |   v2    +---------+    +---+
 |   +--------->service-2+-+-->pod|
 +---+         +---------+ |  +---+
                           |
ingress                    |  +---+
                           +-->pod|
                              +---+
```

## Apply resources

```bash
# hello world namespaces
kubectl create ns hello-world
# hello world deployments
kubectl apply -f deployments -n hello-world
# hello world service
kubectl apply -f service -n hello-world
# hello world ingress depends on your ingress class such as gce, nginx
kubectl apply -f ingress/<your-ingress-class> -n hello-world
```


## reference

https://cloud.google.com/kubernetes-engine/docs/how-to/load-balance-ingress#multiple_backend_services
