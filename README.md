# Winter-rails

```sh

echo "
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-updates main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-backports main restricted universe multiverse
  deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ jammy-security main restricted universe multiverse
" > /etc/apt/sources.list

export DEBIAN_FRONTEND=noninteractive

apt update -y

apt install -y rails ruby-xpath libyaml-dev ruby-tzinfo

if [ ! -d ~/Winter-rails ]; then cd ~/ ; git clone https://github.com/AndyInAi/Winter-rails.git; fi

cd  ~/Winter-rails

gem sources --add http://mirrors.tuna.tsinghua.edu.cn/rubygems/ --remove https://rubygems.org/

gem install xpath

bundle config mirror.https://rubygems.org https://gems.ruby-china.com

bundle install

chmod +x bin/rails

bin/rails server -b 0.0.0.0 -p 8080

# starting HTTP server at http://0.0.0.0:8080

```
