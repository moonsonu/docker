FROM debian
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install wget -y
RUN apt-get install bzip2 -y
RUN wget http://dl.4players.de/ts/releases/3.2.0/teamspeak3-server_linux_amd64-3.2.0.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.2.0.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.2.0.tar.bz2
EXPOSE 9987/udp 10011 30033
CMD ["sh", "teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# docker build -t ex01 .
# docker run -it --rm --name ex1 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 10011:10011 -p 30033:30033 teamspeak
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-debian-9-stretch
