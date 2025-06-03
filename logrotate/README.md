# Ansible para configurar logrotate 

## Instalar

Dentro el archivo inventory.ini agregar la siguiente estructura:

[debian_servers]
192.168.10.1 ansible_user=tu_usuario

```bash
ansible-playbook -i inventory.ini  logrotate_playbook.yml                                                                                                                                              
```

## Test 


Para probar una configuracion en un entorno controlado, se recomienda hacer los siguientes pasos: 

Haciendo uso del Dockerfile ubicado dentro de la carpera logrotate. 

```bash 
docker build  -t test/ssh    --platform linux/amd64 -f Dockerfile .
```

* Use  --platform linux/amd64 para MacOS sillicon 

Dentro del archivo inventory.ini agregar:

```yaml
[docker]
test/ssh ansible_host=localhost ansible_port=2222 ansible_user=ansible ansible_password=ansible ansible_python_interpreter=/usr/bin/python3
```

Modificar dentro del archivo logrotate_playbook.yml hosts: debian_servers por hosts: docker. Luego ejecutar:

```bash
ansible-playbook -i inventory.ini  logrotate_playbook.yml
```