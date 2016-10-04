# Team Red - Infrastructure & Deployment

This repoitory contains Ansible roles and playbooks to set up Team Red's infrastructure.

Playbooks are called `setup-<SNAPSHOT_NAME>` where `SNAPSHOT_NAME` is the name of a
vSphere or VirtualBox snapshot that was created from that playbook.

### Requirements

The playbooks have been tested on CentOS 6.8.

### How to use

Before running a playbook that contains the *git* role, enter Team Red GitHub credentials and desired passphrase for SSH key generation in `roles/git/vars/main.yml`.

Make sure you have the correct VM(s) selected for the `hosts` property of the playbook.

Run a playbook with:

    ansible-playbook <PLAYBOOK_NAME> -i inventory -k

### Roles

#### git

Installs git, creates an SSH key pair, and submits the public key to the Team Red CI
GitHub account.

#### accessibility

Configures the machine with Jenkins' public key, so he gains root access.  
Configures iptables rules to open ports that are closed by default.
