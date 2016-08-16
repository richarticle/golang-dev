FROM centos:centos7

COPY vimrc /root/.vimrc
COPY tmux.conf /root/.tmux.conf

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN yum install -y vim tmux wget git && yum -y clean all \
    && wget https://storage.googleapis.com/golang/go1.7.linux-amd64.tar.gz -O golang.tar.gz \
    && tar -C /usr/local -zxf golang.tar.gz \
    && rm -f golang.tar.gz \
    && mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH" \
    && git clone https://github.com/gmarik/Vundle.vim.git /root/.vim/bundle/Vundle.vim \
    && vim +PluginInstall +qall \
    && vim +GoInstallBinaries +qall \
    && rm -rf /go/src/* /go/pkg/*

WORKDIR $GOPATH

CMD ["/bin/bash"]

