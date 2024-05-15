# Gateway

```sh
kubectl --context $KUBECTL_CONTEXT apply -f - <<EOF
apiVersion: gateway.networking.k8s.io/v1
kind: Gateway
metadata:
  name: api-gateway
  namespace: kuadrant-system
  annotations:
    networking.istio.io/service-type: NodePort
spec:
  gatewayClassName: istio
  listeners:
  - allowedRoutes:
      namespaces:
        from: All
    name: api
    hostname: "*.$KUADRANT_ZONE_ROOT_DOMAIN"
    port: 80
    protocol: HTTP
EOF
```

# HostPort

```sh

```