# Instruções para criar sua primeira aplicação Rails
Configurações utilizadas no curso:

Ubuntu 16.04
Ruby 2.4.1
Rails 5.1.3
SQLite 3.11.0

Banco de dados: SQLite

## Preparação do ambiente

### Git
Instale o Git:
```
sudo apt-get update; sudo apt-get install git
```

### Ruby
  Instalaremos o Ruby utilizando o gerenciador [*rbenv*](https://github.com/rbenv/rbenv).

  Instale suas dependências (pode dar um copy-paste em seu terminal):
  ```
  $ sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
  $ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
  $ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
  $ echo 'eval   "$(rbenv init -)"' >> ~/.bashrc
  $ source ~/.bashrc
  $ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
  ```

  Cheque com `type rbenv` se o output está idêntico a este:
  ```shell
  # Output
  rbenv is a function
  rbenv ()
  {
      local command;
      command="$1";
      if [ "$#" -gt 0 ]; then
          shift;
      fi;
      case "$command" in
          rehash | shell)
              eval "$(rbenv "sh-$command" "$@")"
          ;;
          *)
              command rbenv "$command" "$@"
          ;;
      esac
  }
  ```

  Agora, com o rbenv instalado (junto com o plugin ruby-build), instale a versão Ruby que desejar (em nosso caso 2.4.0):
  ```
  rbenv install 2.4.0
  ```

  Configure para utilizar essa versão globalmente:
  ```
  rbenv global 2.4.0
  ```

  Para checar se o Ruby foi instalado corretamente, use:
  ```
  ruby -v
  ```

### Rails
  - Usando o [Rubygems](https://rubygems.org/pages/about), instalaremos primeiramente:

    O próprio Rails:
    ```
    gem install rails
    ```
    E o gerenciador de dependências das gems:
    ```
    gem install bundler
    ```
  - Instalar dependências do banco de dados (SQLite, no caso) e o NodeJS (Rails depende do _JavaScript Runtime_):
    ```
    sudo apt-get install sqlite3 libsqlite3-dev nodejs-dev
    ```

  E agora estamos prontos para começar!

  \*Créditos ao [tutorial da Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-16-04)

## Editores
  Questão pessoal, recomendo 2 editores de texto antes de começarmos a mão na massa. Se tiver algum outro preferido, fique à vontade para utilizá-lo!
  - [Atom](https://atom.io/) -> (Utilizarei este)
  - [Sublime](https://www.sublimetext.com/)

Template utilizado: https://github.com/BlackrockDigital/startbootstrap-clean-blog
