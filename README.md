# Golang Development Environment
This is a container for Go language development. The following features are included
- Centos7 is the base image
- TMUX is installed for convenience with customized .tmux.conf
- VIM is installed with customized .vimrc
- VIM-GO plugin is installed
- NERDTreeTabs plugin is installed for VIM
- Go 1.5.3 is installed
- Automatically goimports on saving files

# Running the Container
To run this container

    docker run -it --name golang --net host --log-driver none richarticle/golang-dev
    
If you want to mount the volume of Go source code

    docker run -it --name golang --net host --log-driver none -v /home/user/go:/go richarticle/golang-dev

# Commands
In this vim configuration, comma (,) is the <Leader> key.
- ,<n>: Go to tab n
- ,b: Go build
- ,r: Go run
- ,n: Toggle NERDTreeTabs
- <C-x><C-o>: Autocompletion
- ,<space>: No highlight
- <F1>|,i: Show information of variables, functions, etc.
- <F2>|,d: Go to definition
- <F3>: GoReferrers
- <F5>: Previous tab
- <F6>: Next tab
- <F12>: Toggle paste mode

Please refer to https://github.com/fatih/vim-go/wiki/Usage for more information.
