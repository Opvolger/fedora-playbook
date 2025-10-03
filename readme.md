# Install new Fedora system

Install ansible

```bash
sudo yum install ansible python3-pip
pip install ansible-dev-tools # for ansible-lint
```

## Install VSCode

```bash
ansible-playbook install-code.yaml --ask-become-pass -vv
```

## Multimedia and tools

[Multimedia](https://rpmfusion.org/Howto/Multimedia)


```bash
ansible-playbook install-tools.yaml --ask-become-pass -vv
```

## Github sshkey

