# General Configuration

### Setup Ansible
> Windows: sob?

> macOS (Homebrew): `brew install ansible ansible-lint`

> Linux: Install `ansible` and `ansible-lint` via your package manager.

### Configuring Box
> Debian (Headless) and Ubuntu Server are the only supported OS's.
1. Ensure your box has a static local IPv4 Address. If it changes, glhf.
2. 

### Set box IP in `inventory`
- Change `69.69.69.69` to the local IPv4 IP.

### Create `default.yaml` and `secrets.yaml`
- Copy `/vars/default.yaml.example` to `/vars/default.yaml`
- Copy `/vars/secrets.yaml.example` to `/vars/secrets.yaml`

### Timezone
- Set `timezone` as per [Wikipedia/List_of_tz_database_time_zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)