# Setup
Setting up Ubuntu on WSL2 with ansible

## Quick Start

```
# Installs ansible and dependencies
sudo sh bootstrap.sh

# Run the playbook
ansible-playbook -K playbook.yaml
```

## What do you get?

### Infrastructure/OPS tooling

- [Docker](https://www.docker.com/): building and running containers
- [Kubectl](https://kubernetes.io/): interacting with Kubernetes clusters
- [Kubeadm](https://github.com/kubernetes/kubeadm): building and managing Kubernetes clusters
- [Terraform](https://www.terraform.io/): building and managing infrastructure
- [Helm](https://helm.sh): building, deploying, and using Helm charts
- [k14s](https://k14s.io/): using ytt (yaml templating), kbld (image building and pushing), kapp (kubernetes application), kwt (workstation tooling)
- [kubectx and kubens](https://kubectx.dev): tools for quickly changing kubernetes contexts and namespaces
- [Skaffold](https://github.com/GoogleContainerTools/skaffold): CLI tool for iterating on Kubernetes applications
## To Do:

- [ ] ruby
- [ ] node
- [ ] elixir
- [ ] asdf
- [ ] rvm
- [ ] kubeps1
- [ ] terragrunt
- [ ] vim
- [ ] fonts
- [ ] zsh?
- [ ] directory management
- [ ] skaffold
- [ ] possibly split applications out from utils/ e.g. cli mode vs full mode
- [ ] tmux
- [ ] vim wiki
- [ ] vim plugins
- [ ] doctl
- [ ] spacemacs?

## Resources
- [Quickstart on how to create local ansible playbooks](https://www.tricksofthetrades.net/2017/10/02/ansible-local-playbooks/)
- [dev-machine](https://github.com/SteveEdson/dev-machine)
