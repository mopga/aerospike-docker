#Aerospike DB cluster in docker-compose with autodiskovery and scaling.

##INSTALL AND RUN

0. You need docker and docker-compose installed in your system. 
    Versions:
    - Docker 18.09.6
    - docker-compose 1.21.0

1. clone the repo

2. run `docker-compose up -d`

3. If you need more then 1 db server use command:
    `docker-compose scale aerospikedb=$number_of_instances`

## TESTING 

To test the succes you can run commands:

`docker exec -it <aerospikedb container> asadm -e info`

for example:

`docker exec -ti aerospike_aerospikedb_1 asadm -e info`

if the cluster is up, you can connect and run commands to store\read data:

`docker exec -ti <meshworker container name> aql -h <aerospike_db container name>`

`insert into dev.foo (PK, foo) values ('123','my string')`
`select * from dev.foo`

