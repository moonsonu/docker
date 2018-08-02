FROM ubuntu

RUN apt-get update -yq \
	&& DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
	ca-certificates \
	openssh-server \
	curl \
	postfix

WORKDIR /
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt-get update && EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ce

RUN apt update && apt install -y tzdata && \
  apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 80

COPY entrypoint.sh /usr/local/bin/
RUN ln -s usr/local/bin/entrypoint.sh
CMD ["bash", "entrypoint.sh"]

# https://hub.docker.com/r/gitlab/gitlab-ce/~/dockerfile/
# https://about.gitlab.com/installation/#ubuntu
# https://gitlab.com/gitlab-org/omnibus-gitlab/issues/2229
#docker build -t e03 .
#docker run -it --rm -p 80:80 --privileged e03
