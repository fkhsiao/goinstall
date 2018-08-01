# goinstall

# It is my process of install golang


$ cd ~/Downloads

$ wget -c https://storage.googleapis.com/golang/go1.10.2.linux-amd64.tar.gz

$ shasum -a 256 go1.10.2.linux-amd64.tar.gz

ead40e884ad4d6512bcf7b3c7420dd7fa4a96140  go1.10.2.linux-amd64.tar.gz

$ sudo tar -C $HOME/.go -xvzf go1.10.2.linux-amd64.tar.gz

$ mkdir -p ~/go_projects/{bin,src,pkg}

$ cd ~/go_projects

$ ls

vim ~/.profile

export GOROOT=$HOME/.go

export GOPATH=$HOME/go_projects

export GOBIN="$GOPATH/bin"

export PATH=$PATH:$GOROOT/bin


$ source ~/.bash_profile

$ go version

$ go env

$ go help

$ mkdir -p ~/go_projects/src/hello

$ vim ~/go_projects/src/hello/hello.go

package main 
import "fmt"
func main() {
fmt.Printf("Hello Go!!\n")
}


vim ~/.bash_aliases

alias goinstall='f(){ `go install $GOPATH/src/"$@"`; unset -f f; }; f'

alias gorun='f(){ $GOBIN/"$@"; unset -f f; }; f'

$ goinstall hello/hello.go

$ gorun hello



