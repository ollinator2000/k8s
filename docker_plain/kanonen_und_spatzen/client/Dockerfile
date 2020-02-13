FROM debian:latest
RUN apt-get update && apt-get install -y curl 
CMD while true ; do curl -s http://timeserver/time.log ; sleep 2 ; done
