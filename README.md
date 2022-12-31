# vmware-ansible

## prerequisite
1. install python
2. install poetry
  - https://python-poetry.org/docs/master/#installing-with-pipx
3. execute below command
```
poetry install
poetry run absible-galaxy collection install -r requirements.yml
```

## parent preparation
```
poetry run ansible-playbook construct.yml -K
```  
It prepares parent VCSA and ESXis.  

## nested deploy
```
poetry run ansible-playbook build.yml
poetry run ansible-playbook deploy.yml -K
```
- The build.yml makes custom iso and upload it to nas datastore.
- The deploy.yml provides nested vcsa and esxis and nsx-t environment.

## lint
- ansible-lint
```
poetry run ansible-lint .
```
- yamllint
```
poetry run yamllint .
```
