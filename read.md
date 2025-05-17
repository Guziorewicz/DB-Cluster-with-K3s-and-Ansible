# Another version of cluser with k3s and helm charts
deps - ansible, helm, k3s, terraform, docker 
usage for - mongo, mongo express, postgres, pgadmin


# commands - INIT
(dry)
ansible-playbook ansible/playbook.yml --tags init,init-dbs,init-gui --check --ask-become-pass

(fully)
ansible-playbook ansible/playbook.yml --tags init,init-dbs,init-gui --ask-become-pass

(partly)

(init infra)
ansible-playbook ansible/playbook.yml --tags init --ask-become-pass

(init DBs)
ansible-playbook ansible/playbook.yml --tags init-dbs

#### BUGGED - possibly problem with ordering
(init GUIs) 
ansible-playbook ansible/playbook.yml --tags init-gui

(cleaning)

(soft, just releases)
ansible-playbook ansible/playbook.yml --tags clean

(full)
ansible-playbook ansible/playbook.yml --tags clean -e reset_k3s=true

# commands - USAGE
