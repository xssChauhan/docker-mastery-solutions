# Using Containers for CLI Testing

##Goal 

* Use different Linux distro containers to check `curl` cli tool version

* Use two different terminal windows to start bash in both `centos:7` and `ubuntu:14.04` using `-it`

* Ensure curl is installed an on latest version for that distro
  - ubuntu : `apt-get update && apt-get install curl`
  - centos : `yum update curl`

* Check curl --version


##Commands

* $ docker container run -it --name ubuntu ubuntu:14.04
  - apt-get update && apt-get install curl
  - curl --version

* $ docker container run -it --name cent centos:7
  - yum update curl
  - curl --version
