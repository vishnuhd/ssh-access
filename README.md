#ssh-access
Grant or Revoke SSH instructions :

### To add a new user and grant user SSH access
ansible-playbook -i inv -e "action=grant" ssh.yml

### To grant SSH access to an existing user (skip adding the user part)
ansible-playbook -i inv -e "action=grant" ssh.yml --skip-tags=add

### To revoke SSH access from an existing user (skip removing the user)
ansible-playbook -i inv -e "action=revoke" ssh.yml --skip-tags=remove

### To remove user, and thereby revoking the SSH access as well
ansible-playbook -i inv -e "action=revoke" ssh.yml


## P.S.
1. Please make sure to add IPs or DNS of target servers in inv file.
2. Update the variabale "user_name" and "user_des" in inv file.
3. Create a directory under "keys" directory having the same name as "user_name" and put its SSH public key in it.