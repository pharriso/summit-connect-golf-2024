AAP config for EDA and controller
=========

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
