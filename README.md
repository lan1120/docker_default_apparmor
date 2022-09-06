# docker_default_apparmor
After v1.13, Docker now generates docker-default in tmpfs, loads it into the kernel using apparmor_parser, and deletes the file.<br>
docker_default_apparmor can help you to obtain docker-default apparmor!
Please 

### (1) check the docker_default that have been loaded to the kernel
![image](https://user-images.githubusercontent.com/24563500/188624499-7d643485-23b0-4ced-bfbc-34630925cccb.png)

### (2) Create a working directory 
mkdir /tmp/docker/<br>
cd /tmp/docker/
copy docker-default-tmp to /tmp/docker/

### (3) Delete the docker_default that have been loaded to the kernel
apparmor_parser -R docker-default-tmp<br>
Then you can not find docker_default when execute apparmor_status
![image](https://user-images.githubusercontent.com/24563500/188624719-3fb2ba94-46e0-45c9-a1dd-bfec2ebaf7e7.png)

### (4) Backup copy /sbin/apparmor_parser
cp -p /sbin/apparmor_parser /tmp/docker/apparmor_parser.bk

### (3) Copy the new apparmor_parser to /sbin/

### (5) Create a container
docker run -it --rm 4179ca8f538c bash

### (6) You can obtain the real docker_default in /tmp/docker/
![image](https://user-images.githubusercontent.com/24563500/188606514-04f0a864-ecca-443c-a1ef-477b94ff3da1.png)

### (7) Don't forget to restore the environment
