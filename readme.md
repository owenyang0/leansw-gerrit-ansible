# Gerrit Ansible Scripts

## Provision
The default provision when start vagrant was disabled. You can just run followings command independently.

```bash
// make sure you updated your hosts file
ansible-playbook gerrit.yml -i hosts -vvvv
```

## HowToUse
1. update your hosts file
2. change `hosts`, `remote_user`, `gerrit_url` in gerrit.yml file
3. run command like above