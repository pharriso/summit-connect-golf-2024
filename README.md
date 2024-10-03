London Summit Connect 2024 - Ansible Golf Demo
=========

This repo contains the configuration for the Ansible Golf Demo.

Setting up the demo on the pi
=========

Pre-req - obtain the IP address for the raspberry pi.


Starting the containers.

```
cd /home/golf/golf/ansible-golfs
podman-compose up
```

Scanning for golf balls.

```
cd /home/golf/golf/ansible-golfs
source ../venv/bin/activate
python app/scan.py "^PL2B.*"
```

Starting the app.

```
cd /home/golf/golf/ansible-golfs
source ../venv/bin/activate
python app/main.py -m localhost:1883 -g PL2BSOMEID:golfball1 | tee output.log
```
