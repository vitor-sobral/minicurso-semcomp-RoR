# Minicurso 'Introdução ao Ruby on Rails' edição Semcomp 20
Minicurso cuja proposta é trazer um breve conhecimento sobre o mundo do Desenvolvimento Web, através do uso do consagrado Framework Ruby on Rails
## Instruções de preparação do ambiente
### Configurações utilizadas neste curso

Ubuntu 16.04

Ruby 2.4.1

Rails 5.1.3

PostgreSQL 9.5.8

### Instalando programas necessários

#### Git
Instale o Git:
```
sudo apt-get update; sudo apt-get install git
```

#### Ruby
Instalaremos o Ruby utilizando o gerenciador [_rbenv_](https://github.com/rbenv/rbenv):
```
sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval   "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

Cheque se a instalação foi ocorrida com sucesso, usando `type rbenv`. O _output_ deve estar parecido com este:
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

Agora, com o rbenv instalado (junto com o plugin ruby-build), instale a versão Ruby que desejar (em nosso caso 2.4.1):
```
rbenv install 2.4.1
```

Configure para utilizar essa versão globalmente (em qualquer local do _File System_):
```
rbenv global 2.4.1
```

Para checar se o Ruby foi instalado corretamente, use:
```
ruby -v
```

#### Rails
- Usando o [Rubygems](https://rubygems.org/pages/about), instalaremos primeiramente:

  - O próprio Rails:
  ```
  gem install rails
  ```
  - E o gerenciador de dependências das gems:
  ```
  gem install bundler
  ```
- Instalar dependências do banco de dados (PostgreSQL, no caso) e o NodeJS (Rails depende do _JavaScript Runtime_ do Node):
```
sudo apt-get install postgresql postgresql-server-dev-all nodejs-dev
```

- Criar usuario no banco:
```
sudo -u postgres createuser -s <pguser>
```

**E agora estamos prontos para começar!**

\*Créditos ao [tutorial da Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-16-04)

### Editores de texto
Questão pessoal. Recomendo estes 2 editores de texto antes de colocarmos a mão na massa. Mas claro, se tiver algum outro preferido, fique à vontade para utilizá-lo!
- [Atom](https://atom.io/) -> (Utilizarei este)
- [Sublime](https://www.sublimetext.com/)

### Template
O template HTML utilizado faz uso do [Bootstrap](https://getbootstrap.com/) e é open-source: https://github.com/BlackrockDigital/startbootstrap-clean-blog

## Referências técnicas
Aqui vai algumas referências dos comandos principais utilizados durante o curso.

### Comandos utilizados no terminal
Para aqueles que ainda não estão familiarizados com o terminal Linux, aqui vai algumas dicas!

#### Lista de comandos principais do Ubuntu (que utilizaremos)

Comando | Significado | Função
--------|-------------|-------
`ls` | list | Lista todos os arquivos e diretórios que se encontram no diretório atual
`cd <directory>` | change directory | Troca o diretório atual para `<directory>`
`cat <file>` | concatenate | Mostra o conteúdo de `<file>`
`sudo <command>` | super user do | Utiliza `<command>` no modo Super Usuário (a.k.a. "Executar como admin")
`apt-get install <package>` || Instala `<package>` no sitema
`reset` || Reseta o terminal (útil para limpar a tela)

\*Para abrir o terminal, procure na lista de aplicativos ou use o atalho `[Ctrl]+[Alt]+[T]`

#### Lista de comandos Git utilizados (que tal aprender um pouquinho de Git também? :smile:)

Comando | Função
--------|-------
`git status` | Checa as mudanças ocorridas nos arquivos desde o último _commit_
`git branch` | Lista todas as _branches_ existentes e indica qual delas você está utilizando
`git checkout <branch>` | Troca de sua _branch_ atual para `<branch>`
`git add <directory/file>` | Adiciona `<directory/file>` à area de _Stage_
`git commit` | Cria um novo _commit_ com as alterações que estão na área de _Stage_
`git pull <remote> <branch>` | Atualiza sua _branch_ atual com as informações novas de `<remote>/<branch>`
`git push <remote> <branch>` | Joga suas alteraçes para o repositório remoto `<remote>/<branch>`

#### Lista de comandos Rails
Comando | Atalho | Função
--------|--------|-------
`rails new <app_name>` || Cria uma nova aplicação Rails com o nome `<app_name>`
`rails server` | `rails s` | Inicia o servidor
`rails console` | `rails c` | Inicia o console da aplicação
`rails generate <GENERATOR> <args>` | `rails g <GENERATOR> <args>` | Gera arquivos necessários de acordo com o `<GENERATOR>` escolhido

##### Lista de Generators (apenas os que vamos utilizar)
- controller
- model
- migration

## Deploy
Heroku é uma ótima plataforma de hospedagem para aplicações Ruby on Rails. Vejamos como podemos fazer uso dele...

* [Instalar ferramenta do Heroku](https://devcenter.heroku.com/articles/heroku-cli)
* 
