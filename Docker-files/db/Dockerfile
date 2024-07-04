FROM mysql:8.0.33
LABEL "Project"="Vprofile"
LABEL "Author"="Janrey"


#we need to set the password while building this image using ENV
#ENV variables are all in the documentation
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"
#when the comes up it's gonna create a database with the name "accounts"

#we will add the db_backup.sql to docker-entrypoint-initdb.d/db_backup.sql to initialize fresh fresh instance
#files with .sh, .sql and .sql.gz that are found in dock-entrypoint will be executed when the container is started. 
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
