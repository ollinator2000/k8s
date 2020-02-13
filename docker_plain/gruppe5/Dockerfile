FROM debian:latest AS source_container
RUN apt-get update
RUN apt-get install -y cowsay
RUN apt-get install -y fortune-mod
RUN /usr/games/cowsay "$(/usr/games/fortune)"> /tmp/cowsay2_out.txt

FROM centos:latest AS multistage
RUN yum -y install httpd
COPY --from=source_container /tmp/cowsay2_out.txt /var/www/html/cowsay_out.txt
CMD /usr/sbin/httpd -DFOREGROUND
