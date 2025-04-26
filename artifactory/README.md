## Installation and Setup

Create your Artifactory home directory and an empty `system.yaml` file. The user creating the folder should be the user running the docker run.

Note
The following steps assume that 
`$JFROG_HOME`
 environment variable is created in the system. For the correct location of 
`$JFROG_HOME`
, see JFrog Product Directory Structure.
```shell
mkdir -p $JFROG_HOME/artifactory/var/etc/
cd $JFROG_HOME/artifactory/var/etc/
touch ./system.yaml
sudo chown -R 1030:1030 $JFROG_HOME/artifactory/var
```
Run the following command in addition if you are using Docker on a Mac machine.

`sudo chmod -R 777 $JFROG_HOME/artifactory/var`


Configure a connection to external database.

For Non-Production environment, you can start an PostgreSQL container on the same machine as Artifactory Container:

`docker run --name postgres -itd -e POSTGRES_USER=artifactory -e POSTGRES_PASSWORD=password -e POSTGRES_DB=artifactorydb -p 5432:5432 library/postgres:16.8`

Configure the `system.yaml` file with the database configuration details:

```yaml
shared:
  database:
    driver: org.postgresql.Driver
    type: postgresql
    url: jdbc:postgresql://host.docker.internal:5432/artifactorydb
    username: artifactory
    password: password
```

Start the Artifactory container using the process that is relevant for your system.

You can fetch the version number from here[https://jfrog.com/download-legacy/].


`docker run --name artifactory -v $JFROG_HOME/artifactory/var/:/var/opt/jfrog/artifactory -d -p 8081:8081 -p 8082:8082 releases-docker.jfrog.io/jfrog/artifactory-oss:7.111.4`

Manage Artifactory using native Docker commands.

```shell
docker ps
docker stop artifactory
```
Access Artifactory from your browser at: `http://SERVER_HOSTNAME:8082/ui/`

For example, on your local machine: `http://localhost:8082/ui/`

Check the Artifactory log.

`docker logs -f artifactory`

Change the default admin password.

The default user will have the following credentials predefined in the system:

User: `admin`

Password: `password`