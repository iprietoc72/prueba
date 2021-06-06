FROM registry.access.redhat.com/ubi8
LABEL io.k8s.display-name="display-name ivan" \
      io.k8s.description="descripcion ivan" \
      io.openshift.tag="apache,ivan" \
      io.openshift.expose-services="8080:http" 
#comentario
#comentario1
RUN yum install -y httpd && \
    yum clean all && \
    sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && \
    mkdir -p /directorio && \
    chgrp -R 0 /directorio && \
    chmod -R g+rxw /directorio 
COPY index.html /var/www/html/
EXPOSE 8080
VOLUME /directorio
CMD ["httpd","-D","FOREGROUND"]
