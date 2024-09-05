
# Mosquitto as a container

## Installing

``ansible-playbook --private-key ~/.ssh/aap -i invent.yaml -b remote.yaml``

## Starting/Stopping etc

``machinectl shell --uid mosquitto``

``systemctl --user start|stop|restart mosquitto.service``

## Checking out the messages

Enter the container then you can publish or subscribe to the topic to send/check messages.

``podman exec -it mosquitto /bin/sh``

### Publish a message

``mosquitto_pub -h localhost -t 'ansible-golfs/golfball/' -m '{"data": "ST_MAGNET_STOP", "stroke": 2}'``
``mosquitto_pub -h localhost -t 'ansible-golfs/golfball/' -m '{"data": 0, "stroke": 1}'``

### Watch the topic

``mosquitto_sub -h localhost -t 'ansible-golfs/golfball/#'``

## Manual Podman command

Create the directories you wish to mount and use them in the -v part of the below.

``podman run --rm -it -p 1883:1883 -v /home/aap/mosquitto/data:/mosquitto/data:Z -v /home/aap/mosquitto/conf/mosquitto.conf:/mosquitto/config/mosquitto.conf:Z -v /home/aap/mosquitto/logs/:/mosquitto/log/:Z --name mosquitto docker.io/library/eclipse-mosquitto:latest``
