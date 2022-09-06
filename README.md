# docker_default_apparmor
After v1.13, Docker now generates docker-default in tmpfs, loads it into the kernel using apparmor_parser, and deletes the file.
Help you to obtain docker-default apparmor!

### (1) Create a working directory 
mkdir /tmp/docker/

### (2) Backup copy /sbin/apparmor_parser
cp -p /sbin/apparmor_parser /sbin/apparmor_parser.bk

### (3) Copy new apparmor_parser to /sbin/

### (4) Delete the docker_default that have been loaded to the kernel
/tmp/docker/apparmor_parser.bk -R docker-default-tmp<br>
then you can not find docker_default when execute apparmor_status

### (5) Create a container
After v1.13, Docker now generates docker-default in tmpfs, loads it into the kernel using apparmor_parser, and deletes the file.

### (6) You can obtain the real docker_default in /tmp/docker/
![image](https://user-images.githubusercontent.com/24563500/188606514-04f0a864-ecca-443c-a1ef-477b94ff3da1.png)

### (7) Don't forget to restore the environment
