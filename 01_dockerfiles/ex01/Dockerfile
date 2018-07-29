FROM debian
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install wget -y
RUN apt-get install bzip2 -y
RUN wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.1.1.tar.bz2
CMD ["sh", "teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# docker build -t ex01 .
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-debian-9-stretch
