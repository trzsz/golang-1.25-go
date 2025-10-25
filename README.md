# golang-1.25-go for trusty

### install

```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:trzsz/golang
sudo apt update
sudo apt install golang-1.25-go
```

### publish

```
wget https://go.dev/dl/go1.25.3.src.tar.gz
tar -xzf go1.25.3.src.tar.gz

rm -rf go/src/crypto/internal/sysrand/internal/seccomp

cd go
debuild -d -S -k$DEBSIGN_KEYID | tee /tmp/debuild.log 2>&1

cd ..
dput ppa:trzsz/golang golang-1.25-go_1.25.3_source.changes
```
