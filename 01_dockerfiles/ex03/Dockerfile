FROM ubuntu

RUN apt-get update -yq \
	&& DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
	ca-certificates \
	openssh-server \
	wget \
	apt-transport-https \
	vim \
	nano \
	gnupg

RUN wget -q -O - https://packages.gitlab.com/gpg.key | apt-key add -
RUN apt-get update && apt-get install -yq --no-install-recommends gitlab-ce

RUN mkdir -p /opt/gitlab/sv/sshd/supervise \
	&& mkfifo /opt/gitlab/sv/sshd/supervise/ok \
	&& chmod a+x /opt/gitlab/sv/sshd/run \
	&& ln -s /opt/gitlab/sv/sshd /opt/gitlab/service \
	&& mkdir -p /var/run/sshd

RUN mkdir -p /assets/ && \
	cp /etc/gitlab/gitlab.rb /assets/gitlab.rb

EXPOSE 443 80 22
VOLUME ["/etc/gitlab", "/var/opt/gitlab", "/var/log/gitlab"]
COPY assets/wrapper /usr/local/bin/
CMD ["/usr/local/bin/wrapper"]

# https://hub.docker.com/r/gitlab/gitlab-ce/~/dockerfile/
#docker build -t e03 .
#docker run -it --rm -p 80:80 -p 21:22 --privileged e03
