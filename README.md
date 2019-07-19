# Setup
Ansible Playbooks for setting up an ops/ruby/elixir/node focused workstation.

Used on:
- [WSL2](https://devblogs.microsoft.com/commandline/announcing-wsl-2/) with the [Ubuntu app ](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab)

For information on how to enable WSL2, check out this handy [post](https://www.thomasmaurer.ch/2019/06/install-wsl-2-on-windows-10/?source=post_page---------------------------)
## Quick Start

```
# Installs ansible and dependencies
sudo sh bootstrap.sh

# Run the playbook
ansible-playbook -K playbook.yaml
```

## What do you get?

### Ops tooling

> Tooling for doing operations and infrastructure type tasks. Mostly focused on interacting with cloud providers and working with Kubernetes and Docker.

- [Docker](https://www.docker.com/): building and running containers
- [Kubectl](https://kubernetes.io/): interacting with Kubernetes clusters
- [Kubeadm](https://github.com/kubernetes/kubeadm): building and managing Kubernetes clusters
- [Terraform](https://www.terraform.io/): building and managing infrastructure
- [Helm](https://helm.sh): building, deploying, and using Helm charts
- [k14s](https://k14s.io/): using ytt (yaml templating), kbld (image building and pushing), kapp (kubernetes application), kwt (workstation tooling)
- [kubectx and kubens](https://kubectx.dev): tools for quickly changing kubernetes contexts and namespaces
- [Skaffold](https://github.com/GoogleContainerTools/skaffold): CLI tool for iterating on Kubernetes applications

### Dev tooling

> Tooling and programming languages for scripting and application development.

- [asdf](https://asdf-vm.com/#/): version manager for multiple languages, frameworks, and plugings (think nvm, rbenv)
- [ruby](https://www.ruby-lang.org/en/): "A dynamic, open source programming language with a focus on simplicity and productivity."
- [erlang](https://www.erlang.org/): "Erlang is a programming language used to build massively scalable soft real-time systems with requirements on high availability."
- [elixir](https://elixir-lang.org/): "Elixir is a dynamic, functional language designed for building scalable and maintainable applications."

## To Do:

- [ ] node
- [ ] kubeps1
- [ ] terragrunt
- [ ] vim
- [ ] fonts
- [ ] zsh?
- [ ] directory management
- [ ] possibly add gui applications for a native linux install? e.g. cli mode vs full mode
- [ ] tmux
- [ ] vim wiki
- [ ] vim plugins
- [ ] doctl
- [ ] spacemacs?

## Resources
- [Quickstart on how to create local ansible playbooks](https://www.tricksofthetrades.net/2017/10/02/ansible-local-playbooks/)
- [dev-machine](https://github.com/SteveEdson/dev-machine)
