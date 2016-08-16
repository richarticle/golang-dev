FROM centos:centos7

COPY vimrc /root/.vimrc

ENV GOPATH /go
ENV PATH /root/vimgobin/:$GOPATH/bin:/usr/local/go/bin:$PATH

RUN yum install -y vim wget git && yum -y clean all \
    && wget -q https://storage.googleapis.com/golang/go1.7.linux-amd64.tar.gz -O golang.tar.gz \
    && tar -C /usr/local -zxf golang.tar.gz \
    && rm -f golang.tar.gz \
    && mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH" \
    && git clone https://github.com/gmarik/Vundle.vim.git /root/.vim/bundle/Vundle.vim \
    && vim +PluginInstall +qall \
    && rm -rf /go/src/* /go/pkg/*

WORKDIR $GOPATH

CMD ["/bin/bash"]

