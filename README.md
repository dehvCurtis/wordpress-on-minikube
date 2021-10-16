# wordpress-on-minikube

## description

This project deploys a WordPress site and a MySQL database using Minikube. Both applications use `PersistentVolumes` and `PersistentVolumeClaims` to store data

## files

- [mysql-deployment.yaml](https://github.com/dehvCurtis/wordpress-on-minikube/blob/main/mysql-deployment.yaml)
- [wordpress-deployment.yaml](https://github.com/dehvCurtis/wordpress-on-minikube/blob/main/wordpress-deployment.yaml)

## pre-reqs

- minikube installed
- kubectl installed

## `PersistentVolumeClaims` and `PersistentVolumes`

MySQL and Wordpress each require a PersistentVolume to store data. Their PersistentVolumeClaims will be created at the deployment step, as they have already been added to the deployment yamls.

## Create a `kustomization.yaml`

### Add a Secret Gen

A Secret is an object that stores a piece of sensitive data like a password or key. You can create a Secret by generators in `kustomization.yaml`

1. add password to `$WPPASS` env var
2. run `./secret-gen.sh` script