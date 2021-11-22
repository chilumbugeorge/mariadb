*NOTE: 
 - Replication user is already created in the docker-compose file <master-x/secrets/account.sql>
 - MySQL my.cnf file is already copied from <master-x/conf.d/my.cnf> file each container </etc/mysql/mariadb.conf.d/>
     - The my.cnf does includes all the variables that i normally tune. Most of them are already tuned, but some would depend on the power of the system e.g., innodb_buffer_pool_size.  
 - Inside the repo, there is a docker-compose.yaml which can be run with the following commands:
     - docker-compose up     # To create containers with database nodes for replication
     - docker-compose down   # To stop and remove the containers
 - For replication, with setup instructions below, use binary file and position, and not with GTID setup.   
 - Since replication assumes a new environment with no initial data, the sectup via docker-compose automatically creates a replication user for both Master-1 and Master-2, and this simplifies in making each master the slave of the other without having to take backups.
