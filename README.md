# ERESEARCH REPOSITORY PLATFORM

![](e-research.gif)


### Description
This is a convenient repository, which holds a docker compose file,
which starts up the whole repository platform.

In order to run the docker compose file, first you need to
create docker images for the following services (instructions are on README.md of every service):

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



### TODOs
* mongodb data for all CS teiath academics.

