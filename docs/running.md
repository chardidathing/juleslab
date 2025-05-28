# Running Playbooks

### Time to run :3
```
ansible-playbook -K -i ./inventory ./main.yaml
```

### What it do?
`-K` - Ask for become password (sudo password)

`-i ./inventory` - Specify inventory file