Install ansible (on your local):
	$ apt install ansible

put servers addresses in hosts under [master] or [worker]


execute initial.yml (optional):
	$ ansible-playbook -i hosts initial.yml


install Docker, install APT Transport HTTPS, add Kubernetes apt-key, add Kubernetes' APT repository, install kubelet, install kubeadm on all servers and install kubectl on master:
execute kube-dependencies.yml:
	$ ansible-playbook -i hosts kube-dependencies.yml


initialize the cluster, create .kube directory, copy admin.conf to user's kube config, install Pod network (flannel) on master:
execute master.yml:
	$ ansible-playbook -i hosts master.yml


get join command and set join command on master and join the workers to cluster:
execute worker.yml:
	$ ansible-playbook -i hosts worker.yml
