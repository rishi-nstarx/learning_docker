FROM nginx:1.27.0

# RUN apt-get update

# # Here -y for 'yes' as it comes across installing the 'vim'.
# RUN apt-get -y install vim

COPY index.html usr/share/nginx/html/index.html

# Changing the ownership of index.html file to nginx user.(but in my case it was not required.)
RUN chown nginx:nginx usr/share/nginx/html/index.html

