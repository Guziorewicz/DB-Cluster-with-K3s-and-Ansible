# Example of cluster with k3s and helm charts
deps - ansible, helm, k3s, terraform, docker 

usage for - mongo, postgres with prometheus


# commands - INIT
(dry)
ansible-playbook ansible/playbook.yml --tags init,init-dbs --check --ask-become-pass

(fully)
ansible-playbook ansible/playbook.yml --tags init,init-dbs --ask-become-pass

(partly)

(init infra)
ansible-playbook ansible/playbook.yml --tags init --ask-become-pass

(init DBs)
ansible-playbook ansible/playbook.yml --tags init-dbs


(cleaning)

(soft, just releases)
ansible-playbook ansible/playbook.yml --tags clean

(full)
ansible-playbook ansible/playbook.yml --tags clean -e reset_k3s=true


# commands - USAGE


prometheus

kubectl port-forward svc/prometheus-server 9090:80

(in browser)

http://localhost:9090/

postgres

kubectl exec -it statefulset/postgresql -- psql -U postgres -d devdb

mongo - server only


# Metrics

kubectl top pods

kubectl top nodes

# Monitoring

kubectl get nodes

kubectl get pods -A
