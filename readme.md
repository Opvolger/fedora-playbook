# Install new Fedora system

Install ansible

```bash
sudo yum install ansible python3-pip git
pip install ansible-dev-tools # for ansible-lint
git clone https://github.com/Opvolger/fedora-playbook.git
cd fedora-playbook
ssh-keygen -t ed25519 -C "bas@opvolger.net" # create new ssh-key
```

create file `~/.ansible.cfg`

```ini
[defaults]
host_key_checking = False
hash_behaviour=merge
callbacks_enabled = profile_tasks, timer
private_key_file = ~/.ssh/id_ed25519
stdout_callback = yaml
forks=15
pipelining = True

[ssh_connection]
ssh_args = -o ControlMaster=auto -o ControlPersist=60s
```

## Install VSCode

```bash
ansible-playbook install-code.yaml --ask-become-pass -vv
```

## Install Slack

```bash
ansible-playbook install-slack.yaml --ask-become-pass -vv
```

## Multimedia and tools

[Multimedia](https://rpmfusion.org/Howto/Multimedia)


```bash
ansible-playbook install-tools.yaml --ask-become-pass -vv
```

## Github sshkey

Add SSH key for machine

```bash
cat ~/.ssh/id_ed25519.pub
```