# Local Kubernetes Cluster using kubeadm , Vagrant , Ansible:

Create a Kubernetes Cluster using kubeadm, Ansible, and Vagrant : 1 Master , 2 Workers

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Project Structure](#project-structure)
- [Installation](#installation)
  - [Vagrant Setup](#vagrant-setup)
- [Usage](#usage)
- [Contributing](#contributing)


## Overview

This project aims to provide an automated way to create a Kubernetes cluster using kubeadm, Ansible, and Vagrant. It simplifies the process of setting up a development or testing Kubernetes environment on your local machine. You can quickly spin up a multi-node Kubernetes cluster for experimentation and development.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Vagrant**: Make sure Vagrant is installed on your system. You can download it from [https://www.vagrantup.com/](https://www.vagrantup.com/).

- **VirtualBox**: You'll need VirtualBox as the provider for Vagrant. Install it from [https://www.virtualbox.org/](https://www.virtualbox.org/).

- **Ansible**: Ensure Ansible is installed on your local machine. You can install it following the instructions at [https://docs.ansible.com/ansible/latest/installation_guide/index.html](https://docs.ansible.com/ansible/latest/installation_guide/index.html).

- **Git**: You should have Git installed to clone this repository and manage the project.

## Getting Started

To get started with this project, follow these steps:

### Project Structure

The project directory structure is as follows:

```plaintext
├── .kube
├── .vagrant
│   ├── machines
│   │   ├── master
│   │   │   └── virtualbox
│   │   └── worker1
│   │       └── virtualbox
│   └── rgloader
├── group_vars
└── roles
    ├── cni
    │   ├── defaults
    │   ├── tasks
    │   └── templates
    ├── commons
    │   ├── os-checker
    │   │   ├── defaults
    │   └── tasks
    │   └── pre-install
    │       ├── defaults
    │       ├── tasks
    │       └── templates
    ├── containerd
    │   ├── handlers
    │   └── tasks
    ├── kubernetes
    │   ├── master
    │   │   └── tasks
    │   └── node
    │       ├── handlers
    │       └── tasks
    ├── locale
    │   ├── defaults
    │   ├── tasks
    │   ├── templates
    │   └── vars
    └── ntp
        ├── defaults
        ├── handlers
        ├── tasks
        ├── templates
        └── vars
```
## Installation

To set up the Kubernetes cluster, follow these installation steps:

### Vagrant Setup

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/AlaaTriaa/Automated_K8S_Cluster.git
   ```
   
2.Change to the project directory:

```bash
    cd Automated_K8s_Cluster
```


3. Modify the Vagrantfile in the project root to adjust the number of nodes and their configuration as needed.

Start the Vagrant virtual machines:
```bash
  vagrant up
```



## Usage:
You can now start using your Kubernetes cluster for development, testing, or experimentation. Use kubectl to interact with the cluster:

```bash
    kubectl get nodes
    kubectl get pods --all-namespaces
    # ... and more
```

## Contributing
Contributions are welcome! If you have any improvements or suggestions for this project, please open an issue or create a pull request.


