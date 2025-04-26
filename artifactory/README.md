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
