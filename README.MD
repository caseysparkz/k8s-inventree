# inventree-kubernetes

This repository provides manifests for easily deploying InvenTree to Kubernetes.


## Setup

1. Edit `inventree-config.yml` and change the values for `INVENTREE_ADMIN_USER`
    and `INVENTREE_ADMIN_EMAIL` if desired.
1. Deploy the namespace, configurations, and secrets with: `kubectl apply -f
    ./inventree-config.yaml`
1. Edit the `INVENTREE_DB_PASSWORD` and `INVENTREE_ADMIN_PASSWORD` with
    `kubectl edit secrets --namespace inventree inventree`.
1. Deploy all other resources with `for F in ./*.yml; do kubectl apply -f $F; done`
