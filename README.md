# pilot_project

WIP: Automatic deployment of load balanced web app with K8S, deployed with Vagrant & Ansible, monitored with Prometheus & Grafana
If anyone sees this, please note that I am still learning and that the following todo list is subject to change!

Todo:

- Prepare Vagrantfile for VMs (done):
  - k8s master
  - k8s pod 1
  - k8s pod 2
  - k8s pod 3
  - db server
  - monitoring server

- Automate Prometheus deployment with Ansible (done)
- Automate Grafana deployment with Ansible (done)
- Automate node_exporter deployment with Ansible
- Build basic todo list web app with DB integration
- Deploy Kubernetes cluster with 3 pods, 1 master and DB server outside of the cluster
- Automate deployment of K8S cluster
