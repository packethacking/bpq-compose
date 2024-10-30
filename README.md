# BPQ API Extensions

This repository is a docker-compose file that will bring up the API extension wrappers around [BPQ](https://www.cantab.net/users/john.wiseman/Documents/index.html).

These include:

* [HTTP API](https://github.com/M0LTE/bpqapi/) - Provide a Swagger compatible HTTP API
* [IMAP](https://github.com/packethacking/bpq-imap-bulletins) - Export Personal and Bulletin mail via IMAP
* [Mosquitto](https://mosquitto.org/) - MQTT server for event output

## Starting the services.

```
docker compose up -d
```

This will bring up all the services, hopefully in a sensible state.

## Configuring BPQ

The amount of configuration required in BPQ is minimal, however to take advantage of the MQTT events, some configuration must be added.

```
# Edit /etc/bpq32.cfg
MQTT=1
MQTT_HOST=localhost
MQTT_PORT=1883
MQTT_USER=bpqmon
MQTT_PASS=bpqmon
```

## Security Note

None of these API extensions are encrypted. They also ship with default passwords.
*DO NOT* expose these to the public internet.
