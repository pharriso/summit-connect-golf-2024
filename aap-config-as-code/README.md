AAP config for EDA and controller
=========

Passwords
------------

I didn't want to deal with passwords in this repository so you'll need to manually create the credentials for Slack and the Govee Lights and then re-run the playbook. Or add the credentials to this config before running.


EDA
------------

Setting environment variables for authentication. 

```
export EDA_HOST=
export EDA_USERNAME=
export EDA_PASSWORD=
```

Edit vars in vars/eda_vars as needed. Run the playbook.

```
ansible-playbook eda_config.yml
```

EDA rulebook will need extra vars passing to it:

```bash
mqtt_host: <host>
mqtt_username: <user>
mqtt_password: <password>
```

Again, not wanting to deal with secrets in this repo, you'll need to add these to the rulebook or the config. Captured here though so we know.

Controller
------------

Setting environment variables for authentication. 

```
export CONTROLLER_HOST=
export CONTROLLER_USERNAME=
export CONTROLLER_PASSWORD=
```

Edit vars in vars/controller_vars as needed. Run the playbook.

```
ansible-playbook controller_config.yml
