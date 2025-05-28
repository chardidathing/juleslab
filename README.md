# juleslab
> may be broken, idk. - this is for a friend not for normal use pls it might explode

## Setup

### General Configuration
[docs/general.md](docs/general.md)

### Domain Setup (Caddy w/Cloudflare)
[docs/domain.md](docs/domain.md)

### Running time :3
[docs/running.md](docs/running.md)

### Adding Containers
[docs/adding-containers.md](docs/adding-containers.md)

## ⚠️ Things to note
- IPv6 will be disabled.
- Firewall rules will be configured by this playbook. UFW will be disabled.
- This disables password authentication over SSH. You can change this in `inventory` > `security_ssh_password_authentication: yes`
- This disables root login over SSH. You can change this in `inventory` > `security_ssh_permit_root_login: yes`

## Implemented
- [x] Updates (apt upgrade)
- [x] Docker Installation
- [x] Caddy
- [x] Firewall Rules
- [ ] Other things