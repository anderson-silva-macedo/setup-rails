# setup-rails
Ambiente de desenvolvimento Ruby on rails Ubuntu 18 com Rbenv

# Adicionando repósitorios NODE e YARN'''
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

# Instalando algumas dependencias
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential \
  libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 \ 
  libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common \
  libffi-dev nodejs yarn libsqlite3-dev nodejs

# Instalando o RBENV
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL


git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

# Instalando o Ruby
rbenv install 2.5.1
# Definindo uma versão global
rbenv global 2.5.1
# Ver a versão instalada
ruby -v

# Instalando o bundler
gem install bundler

# Instalando o rails
gem install rails
