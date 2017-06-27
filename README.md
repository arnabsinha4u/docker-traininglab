# Dockerized Docker Training Lab
Docker Training Lab using DIND (Docker in Docker) and Ansible

### How To's:
Bootstrap host and Startup Lab (Default settings: creates 1 dockerlab group, dockerlabuser1 user and one master container for the user)
```
./docker_lab.yml -t baseline,m_build_images,m_startup
```

#### Startup
Startup Lab with default settings:
```
./docker_lab.yml -t users,group,m_startup
```

Scale-up Lab or Start Lab for more users (example 3 users):
```
./docker_lab.yml -t users,group,m_startup -e users=3
```

#### Shutdown
Shutdown Lab with default settings:
```
./docker_lab.yml -t remove_group,remove_users,m_shutdown
```

Scale-down of Shutdown Lab for more users (example 3 users):
```
./docker_lab.yml -t remove_group,remove_users,m_shutdown -e users=3
```

### Caveat
sudoers file to be changed to include dockerlab group without passwords. Example mentioned
This has not been included in the playbook to ensure control and transparency
```
%dockerlab  ALL=(ALL)       NOPASSWD: ALL
```

### Credits:
DIND has been used from: https://github.com/jpetazzo/dind.git
