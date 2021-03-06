# ERESEARCH REPOSITORER PLATFORM

![](e-research.gif)


### Description
This is a convenient repository, which holds a docker compose file,
that starts up the whole eresearch repositorer platform.

In order to run the docker compose file (`docker-compose.yml`), first you need to
create the docker images for the following services (instructions are on README.md of every service):

* Platform services:
    * [eresearch-repositorer-service](https://github.com/chriniko13/eresearch-repositorer-service)
    * [eresearch-author-matcher](https://github.com/chriniko13/eresearch-author-matcher)
    * [eresearch-dblp-consumer](https://github.com/chriniko13/eresearch-dblp-consumer)
    * [eresearch-scidir-consumer](https://github.com/chriniko13/eresearch-sciencedirect-consumer)
    * [eresearch-author-finder](https://github.com/chriniko13/eresearch-author-finder)
    * [eresearch-scopus-consumer](https://github.com/chriniko13/eresearch-scopus-consumer)
    


* When you create the above images you can execute: `docker-compose up` in order to start the containers.

* (Optional) in order to stop the containers, execute: `docker-compose down`

* In order to see specific logs of a container execute: `docker-compose logs -f <container_name>`, eg: `docker-compose logs -f eresearch-dblp-consumer`

* To see all running containers execute: `docker ps`

* To stop a container execute: `docker-compose stop <container_name>`

* To start a container executee: `docker-compose start <container_name>`


### Convenient UI (Admin Portal) in order to run repositorer operations
* [eresearch-repositorer-admin-portal](https://github.com/chriniko13/eresearch-repositorer-admin-portal)



### How to dump MongoDB Eresearch Repositorer Platform data
* Enter in container with bash: `docker exec -it <mongo_container_name> bash`, eg: `docker exec -it eresearchrepositorerplatform_mongo_1 bash`

* Take a dump of eresearch db to a directory: `mongodump --db eresearch --out chriniko/` (Default mongo dump directory is: `dump`)

* Copy the contents of mongo container's directory to a host machine directory: `docker cp eresearchrepositorerplatform_mongo_1:/chriniko/ .`


### How to import MongoDB Ereasearch Repositorer Platform dump data

* First execute: `docker-compose up` in order to start mongodb as a docker container.

* Then in order to load the dump, execute: `mongorestore -h localhost:27017 --db eresearch chriniko/eresearch/`