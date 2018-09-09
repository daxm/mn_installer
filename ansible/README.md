# PIRL Masternode Installer
This installer uses Ansible to configure your system to be a PIRL masternode.

# Steps
*  Install Ansible, git, and python-netaddr on your machine.
   * Debian/Ubuntu: #`apt install -y ansible git python-netaddr`
   * RedHat/CentOS: #`yum install -y ansible git python-netaddr`
*  Copy the env.cfg-sample to env.cfg.  `cp env.cfg-sample env.cfg`
*  Modify the file *env.cfg* file and fix the *MASTERNODE* and *TOKEN* variables to match your setup.  `nano env.cfg`
*  Optional:  In the env.cfg file change the RUNAS_USER variable to be which user you'd like the masternode to run as.
*  If you are root, run the command: `ansible-playbook mn_installer.yml` to start the installation.  This might take 
some time so be patient.
*  If you are not root add a `-K` to the command:  `ansible-playbook -K mn_installer.yml`.

# Troubleshooting
*  During the running of the ansible-playbook command, if it fails you might want to just re-run it.  Occasionally, it 
will fail and re-running it solves the issue.
*  If you messed up your MASTERNODE and/or TOKEN variables you can either change them as describe above and rerun the 
the ansible-playbook command or you can edit the /etc/pirlnode-env file and fix them there.  If you edit that file be 
sure to restart the pirlnode service with: `sudo systemctl restart pirlnode.service`.
