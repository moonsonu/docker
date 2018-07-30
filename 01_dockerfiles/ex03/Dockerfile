FROM debian
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install wget -y
RUN apt-get install git -y
RUN apt-get install gcc -y
RUN apt-get install libpam0g-dev

WORKDIR /home/git
RUN mkdir local
RUN wget https://storage.googleapis.com/golang/go1.10.3.linux-amd64.tar.gz
RUN tar -C /home/git/local -xzf go1.10.3.linux-amd64.tar.gz

ENV GOROOT=/home/git/local/go' >> /home/git/.bashrc
ENV GOPATH=/home/git/go' >> /home/git/.bashrc
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin' >> home/git/.bashrc

RUN mkdir -p $GOPATH/src/github.com/gogs
RUN cd $GOPATH/src/github.com/gogs
RUN git clone --depth=1 -b develop https://github.com/gogs/gogs
RUN go get -u -tags "sqlite pam cert" github.com/gogs/gogs
RUN cd $GOPATH/src/github.com/gogs/gogs
RUN go build -tags "sqlite pam cert"

EXPOSE 3000

CMD ["./gogs", "web"]

# https://gogs.io/docs/installation/install_from_source
