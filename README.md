# IBM Mission
This repository has the code required to achieve the IBM Mission. This repository contains one application which is `hello`, and it's structured in a way to add more applications to it. All applications should be deployed with Ansible on k8s environment
## Pre-requisites
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [Docker](https://docs.docker.com/get-docker/)

## Local Development

### Build
There is on app `hello` which is just static HTML files you can do whatever you want with it.

### Run
1. Rune minikube
```shell
minikube start
```
2. Make sure `kubectl` is configured to use minikube cluster
```shell
kubectl config use-context minikube
```

3. After you are sure minikube cluster is running, run the ansible playbook
```shell
ansible-playbook -i deploy/ansible/hosts deploy/ansible/main.yaml
```

## CI/CD
The CI/CD pipeline is built using Github Actions, and it's triggered on every push to the main branch. The pipeline is defined in `.github/workflows/ci.yaml` file. The pipeline is doing the following: