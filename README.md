# Setup
Ansible Playbooks for setting up an ops/ruby/elixir/node focused workstation.

Used on:
- [WSL2](https://devblogs.microsoft.com/commandline/announcing-wsl-2/) with the [Ubuntu app](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab).
- [Multipass](https://github.com/CanonicalLtd/multipass) on Windows running latest Ubuntu.

For information on how to enable WSL2, check out this handy [post](https://www.thomasmaurer.ch/2019/06/install-wsl-2-on-windows-10/?source=post_page---------------------------)
## Quick Start

```
# Clone to your home directory
git clone git@github.com:jasonwc/setup.git

# Installs ansible and dependencies
sudo sh bootstrap.sh

# Run the playbook
ansible-playbook -K playbook.yaml
```

## What do you get?

### Shell

> Installs basic tools like vim and tmux and sets up zsh as the default shell. Uses my [dotfiles](https://github.com/jasonwc/dotfiles) repo to configure them.

- [zsh](http://zsh.sourceforge.net/): "Zsh is a shell designed for interactive use, although it is also a powerful scripting language."
- [oh-my-zsh](https://ohmyz.sh/): "Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration."
- [vim](https://www.vim.org/): "Vim is a highly configurable text editor for efficiently creating and changing any kind of text."
- [tmux](https://github.com/tmux/tmux): "tmux is a terminal multiplexer: it enables a number of terminals to be created, accessed, and controlled from a single screen. "

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

## Troubleshooting

>  [WARNING] Ansible is in a world writable directory

If you see something like this, you need to set correct permissions on the `setup` directory:

```
 chmod 700 /path/to/setup directory
```

## Inspiration
- [Quickstart on how to create local ansible playbooks](https://www.tricksofthetrades.net/2017/10/02/ansible-local-playbooks/)
- [SteveEdson/dev-machine](https://github.com/SteveEdson/dev-machine)
= [ballPointPenguin/ansible-develop](https://github.com/ballPointPenguin/ansible-develop)
- [Sudo Science - Using Ansible to Set Up Zsh](https://sudo-science.com/using-ansible-to-set-up-zsh/)
