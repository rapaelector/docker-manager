# DOCKER MANAGER ##

Repository of docker compose configurations used by Blubird

## HOSTS

In order to use the general portainer, add the following to your hosts file:
11.88.0.2 develop.eu portainer.develop.eu kibana.develop.eu elastica.develop.eu mailhog.develop.eu

For other projects:
Blubird Website
11.88.0.2 local.blubird.eu new.local.blubird.eu backend.local.blubird.eu api.local.blubird.eu pg.local.blubird.eu

Brand Partners Website
11.88.0.2 crm.local.profilebox.be local.profilebox.be rs.local.profilebox.be api.local.profilebox.be

Skillbench Website
11.88.0.2 local.skillbench.blubird.eu

## TROUBLESHOOTING

### PORTAINER

If you're portainer endpoint is throwing an error, the configuration has probably failed (or accidental deletion..).
The only way I've found to resolve it is by:
* Destroying the container (docker rm main_portainer)
* Build/Up
* Access by IP:PORT : http://11.88.0.3:9000/
* This should direct you to the init page, where we set the configuration to using the local endpoint

All OK