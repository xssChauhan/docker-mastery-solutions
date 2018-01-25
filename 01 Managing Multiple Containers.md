#Managing Multiple Containers
##Goal

* Run a `nginx`, a `mysql` and `httpd` server
* `nginx` should listen on `80:80`, `httpd` on `8080:80`, `mysql` on `3306:3306`
* When running `mysql` , use the `--env` option to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes`

* Use `docker container logs` on mysql to find the random password it created on startup


##Commands

* $ docker container run -d --name mysql -p 3306:3306 --env MYSQL_RANDOM_ROOT_PASSWORD=yes mysql

* $ docker container run -d --name web_n -p 80:80 nginx

* $ docker container run -d --name http -p 8080:80 httpd

* $ docker container ls
