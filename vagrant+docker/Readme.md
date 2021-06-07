## Dockerのインストール
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$  echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update
$ apt install docker-ce=18.06.1~ce~3-0~ubuntu

## Dockerに権限付与
$ sudo usermod -g docker vagrant
$ sudo service docker restart

## ssh接続しなおす
$ exit
$ vagrant ssh

## docker-composeインストール
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

## gitのインストール
$ sudo apt-get install git
$ git config --global user.name [任意のユーザ名]
$ git config --global user.email [任意のユーザ名]