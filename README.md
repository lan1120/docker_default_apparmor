# docker_default_apparmor
Help you to obtain docker default_apparmor!

### (1) Create a working directory 
mkdir /tmp/docker/

### (2) Backup copy /sbin/apparmor_parser
cp -p /sbin/apparmor_parser /sbin/apparmor_parser.bk

### (3) Copy new apparmor_parser to /sbin/

### (4) Delete the docker_default that have been loaded to the kernel
/tmp/docker/apparmor_parser.bk -R docker-default-tmp<br>
then you can not find docker_default when execute apparmor_status

### (5) Create a container

### (6) You can obtain the real docker_default in /tmp/docker/
![image](https://user-images.githubusercontent.com/24563500/188603276-caa2d043-5396-4d8f-97a4-d8547326173e.png)

### (7) Don't forget to restore the environment
