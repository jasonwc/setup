# Setup
Ansible Playbooks for setting up an ops/ruby/elixir focused workstation.

Used on:
- [WSL2](https://devblogs.microsoft.com/commandline/announcing-wsl-2/) with the [Ubuntu app](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6).
- [Multipass](https://github.com/CanonicalLtd/multipass) on Windows running latest Ubuntu.

## (Required) Windows setup
There are a couple easy ways to get to a clean Linux environment on Windows: multipass and WSL.

### WSL2
Follow the [Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

### Multipass
Follow the installation instructions on the [Multipass homepage](https://multipass.run)

## (Required) Docker for Desktop
This workstation won't install the Docker daemon in either the WSL or Multipass. Instead it assumes you have Docker for Desktop running on the Windows side and only installs client libs.

To install Docker for Desktop on Windows, check out [their instructions](https://docs.docker.com/docker-for-windows/install/). For simplicity, I'm running Docker for Desktop with the WSL2.0 backend.

If you're using Multipass, you might have to enable some settings to talk to the Docker socket running in either WSL or on Hyper V. For WSL, it works pretty seamlessly.

## Quick Start
You'll need to get an ssh key into your new Linux environment. Afterwards, run the following:

```bash
# Clone to your home directory
git clone git@github.com:jasonwc/setup.git

# Set your username in playbook.yaml. While you're at it, check out the roles and vars_files too.
# Set your username, repo directory, and repos in user_environment.yml (or clone mine, what do I care!)

# Installs ansible and dependencies
sudo sh bootstrap.sh

# Run the playbook
ansible-playbook -K playbook.yaml
```

## What do you get?
This is a _somewhat_ opinionated but *lean* installation of tools that I want to have on a Linux environment. I do a lot of dev _in_ Docker containers, so often those containers will have specialized tools.

Generally, I'm running this on my primary WSL2 workspace. I also spin up a VM from time to time for specific tasks and provision it with these tools for consistency.

### Shell

> Installs basic tools like vim and tmux and sets up zsh as the default shell. Uses my [dotfiles](https://github.com/jasonwc/dotfiles) repo to configure them.

- [zsh](http://zsh.sourceforge.net/): "Zsh is a shell designed for interactive use, although it is also a powerful scripting language."
- [oh-my-zsh](https://ohmyz.sh/): "Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration."
- [vim](https://www.vim.org/): "Vim is a highly configurable text editor for efficiently creating and changing any kind of text."
- [tmux](https://github.com/tmux/tmux): "tmux is a terminal multiplexer: it enables a number of terminals to be created, accessed, and controlled from a single screen. "
- Syncs from my [dotfiles repo](https://github.com/jasonwc/dotfiles). Loads of config for the basics over there.
- Clones some repos I'm working on

### Ops tooling

> Tooling for doing operations and infrastructure type tasks. Mostly focused on interacting with cloud providers and working with Kubernetes and Docker.

- [Docker](https://www.docker.com/): building and running containers
- [Kubectl](https://kubernetes.io/): interacting with Kubernetes clusters
- [Kubeadm](https://github.com/kubernetes/kubeadm): building and managing Kubernetes clusters
- [Helm](https://helm.sh): building, deploying, and using Helm charts
- [Krew](https://krew.sigs.k8s.io/): Plugin manager for `kubectl`
- Configures `kubectl` with some `krew` plugins I like.

### Dev tooling

> Tooling and programming languages for scripting and application development.

- [asdf](https://asdf-vm.com/#/): version manager for multiple languages, frameworks, and plugings (think nvm, rbenv)
- [ruby](https://www.ruby-lang.org/en/): "A dynamic, open source programming language with a focus on simplicity and productivity."
- [erlang](https://www.erlang.org/): "Erlang is a programming language used to build massively scalable soft real-time systems with requirements on high availability."
- [elixir](https://elixir-lang.org/): "Elixir is a dynamic, functional language designed for building scalable and maintainable applications."
- Handles dependency installation for various languages
- Configurable language versions. Installs whatever is set and sets it globally for easy upgrades.

## Troubleshooting

>  [WARNING] Ansible is in a world writable directory

If you see something like this, you need to set correct permissions on the `setup` directory:

```
 chmod 700 /path/to/setup directory
```

This often happens with WSL installs.

## Inspiration
I learned a lot about Ansible during my time at [Mavenlink](https://github.com/mavenlink). Much of the intial idea came from a great tool maintained by the team there called "ansible-workstation" and its successor "bootstrap-workstation".

These other resources helped me along the way:

- [Quickstart on how to create local ansible playbooks](https://www.tricksofthetrades.net/2017/10/02/ansible-local-playbooks/)
- [SteveEdson/dev-machine](https://github.com/SteveEdson/dev-machine)
- [ballPointPenguin/ansible-develop](https://github.com/ballPointPenguin/ansible-develop)
- [Wintus/Ansible-WSL](https://github.com/Wintus/Ansible-WSL)
- [Sudo Science - Using Ansible to Set Up Zsh](https://sudo-science.com/using-ansible-to-set-up-zsh/)
- [A Linux Dev Environment on Windows with WSL 2, Docker Desktop and More](https://www.youtube.com/watch?v=idW-an99TAM&)
