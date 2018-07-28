FROM debian
RUN apt-get update -y && apt-get upgrade -y
RUN wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.1.1.tar.bz2
CMD ["sh", "ts3server_startscript.sh"]

# docker build -t ex01 .
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-debian-9-stretch
