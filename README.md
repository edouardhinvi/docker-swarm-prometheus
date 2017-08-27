This stack deploys all the components needed to monitor a Docker Swarm cluster:
  - prometheus
  - alertmanager
  - grafana
  - blackbox-exporter
  - docker-exporter
  - node-exporter
  - cAdvisor
  - fregate (free mobile sms api
 
If you want to expose some components through Traefik reverse proxy you first have to have an overlay network with Traefik running in it. In my compose file this overlay network is called "traefik-net"

To deploy the stack run the following command:
```
# docker stack deploy --compose-file prometheus.yml
 prometheus
```

This stack uses configs and secrets. (compose "v3.3")

- Modify the pushover credentials in configs/alertmanager.yml
- Modify the Traefik basic auths and url in promtheus.yml
- If using the free sms api put you username and password in:
    - secrets/fregate_user
    - secrets/fregate_password
