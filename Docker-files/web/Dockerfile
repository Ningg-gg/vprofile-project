FROM nginx
LABEL "Project"="Vprofile"
LABEL "Author"="Janrey"

#same with tomcat we will remove the default configutation file and then copy the "nginvproapp.conf" and place it to the /etc/nginx/conf.d
#so it will become our default application
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf