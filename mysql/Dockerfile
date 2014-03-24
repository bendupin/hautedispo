FROM ubuntu

#RUN dpkg-divert --local --rename --add /sbin/initctl
#RUN ln -s /bin/true /sbin/initctl

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get -y install mysql-server mysql-client
ADD ./hautedispo.sql /tmp/hautedispo.sql
RUN /usr/bin/mysqld_safe & sleep 10s && mysql < /tmp/hautedispo.sql
RUN /etc/init.d/mysql stop
CMD mysql --standalone

EXPOSE 3306

CMD ["/usr/bin/mysqld_safe"]
