# Adding new containers

Creating a new container/service is pretty simple. Jellyseerr is our example here.

- See [playbooks/jellyseerr.yaml.example](../playbooks/jellyseerr.yaml.example) as a reference.
- Refer to [Ansible Docs - community.docker.docker_container module](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_container_module.html#ansible-collections-community-docker-docker-container-module) for all possible options/examples.

### Adding a playbook to the main playbook
Pretty simple - just add it to `main.yaml`
```
- name: Configure Jellyseerr
  ansible.builtin.import_playbook: playbooks/jellyseerr.yaml
```

### Adding service to Caddy
To add a service to Caddy, modify the template in [templates/caddy/Caddyfile.j2](../templates/caddy/Caddyfile.j2)

```
### Jellyseerr
jellyseerr.{{ caddy_domain }} {
    tls {
        dns cloudflare {{ cloudflare_api_token }}
        resolvers 1.1.1.1
    }

    # Enable compression
    encode zstd gzip

    reverse_proxy jellyseerr:5055 {
        header_up X-Forwarded-Proto https
        header_up X-Real-IP {remote_host}
        header_up X-Forwarded-For {remote_host}    
    }
}
```
- Usually the port to reverse proxy to is the HTTP port. If your container supports both, try the HTTP port first.