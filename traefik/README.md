# Traefik

[Traefik](https://traefik.io/) is a modern HTTP reverse proxy and load balancer made to deploy
microservices with ease.

## Introduction

This chart bootstraps Traefik version 2 as a Kubernetes ingress controller,
using Custom Resources `IngressRoute`: <https://docs.traefik.io/providers/kubernetes-crd/>.

## Example Usage

To install Traefik, follow the example below:

```
#!/bin/bash

set -ex

# DNSZone
HOSTNAME=""

# SSL arn for TLS termination at the LB layer
SSL_CERT_ARN=""

# namespace to deploy into
NAMESPACE=""

CROSS_ZONE_LB_ENABLED="true"
SSL_NEGOTATION_POLICY="ELBSecurityPolicy-TLS-1-1-2017-01"

helm template traefik kirk/traefik \
  --namespace="${NAMESPACE}" \
  --set logs.logleve="INFO" \
  --set namespace="${NAMESPACE}" \
  --set dashboard.ingressRoute="true" \
  --set-string service.annotations."external-dns\.alpha\.kubernetes\.io\/hostname"="${NAMESPACE}.${HOSTNAME}" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-backend-protocol"="http" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-cross-zone-load-balancing-enabled"="${CROSS_ZONE_LB_ENABLED}" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-ssl-cert"="${SSL_ARN}" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-ssl-negotiation-policy"="${SSL_NEGOTATION_POLICY}" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-ssl-ports"="*" \
  --set-string service.annotations."service\.beta\.kubernetes\.io\/aws-load-balancer-proxy-protocol"="*"
`
```
