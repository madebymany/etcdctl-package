GIT_URL:=https://github.com/coreos/etcdctl.git
ETCD_SOURCE:=src
GO_PATH:=/usr/local/go

all: $(GO_PATH) $(ETCD_SOURCE) build

$(GO_PATH):
	curl -LSOs http://golang.org/dl/go1.2.2.linux-amd64.tar.gz
	tar -C /usr/local -xf go1.2.2.linux-amd64.tar.gz

$(ETCD_SOURCE):
	git clone $(GIT_URL) $(ETCD_SOURCE)

build:
	export PATH=$$PATH:/usr/local/go/bin && cd $(ETCD_SOURCE) && /bin/bash < build

install:
	install -o root -g root $(ETCD_SOURCE)/bin/etcdctl /usr/local/bin

.PHONY: build
