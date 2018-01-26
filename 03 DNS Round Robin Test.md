#DNS Round Robin Test

##Goals

* Create a new virtual network( default bridge driver )
* Create two containers from `elasticsearch:2` image
* Use `--net-alias search` when creating them to give them an additional DNS name to respond to
* Run `alpine nslookup search` with `--net` to see the two containers list for the smae DNS name
* Run `centos curl -s search:9200` with `--net` multiple times until you see both "name" fields below


##Commands

* $ docker network create my_net
* $ docker container run -d --name els1 --net my_net --net-alias search elasticsearch:2
* $ docker container run -d --name els2 --net my_net --net-alias search elasticsearch:2
* $ docker container run -it --net my_net alpine nslookup search 
* $ docker container run -it --net my_net centos:7 curl -s search:9200
