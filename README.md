GPG Github

+ verifica se tem chaves cadastradas
gpg --list-secret-key --keyid-form LONG

+ gera chave 
gpg --full-generate-key

Escolher tipo da chave e tamanho;
Entrar com o name e email conforme cadastrados no git (git congir user.name e git config user.email para resgatar)
criar senha: MX@123mx
chave gerada

+ pegar chave e vincular no github 
gpg --armor --export BBBA9203FAF9DCA1 (id-da-chave)

copiar do inicio ao fim
acessar o github > config > SSH and GPG Keys > new GPG Key
Adicionar título, colar a chave e  ADD GPG Key

+ configurar chave no terminal (WINDOWS)
git config --global user.signingkey BBBA9203FAF9DCA1
git config --global commit.gpgsign true
git config --global tag.gpgsign true

where gpg (para pagar o caminho do GPG)
C:\Program Files (x86)\GnuPG\bin\gpg.exe

git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
git config --global gpg.program "C:\Users\marcos.xavier\AppData\Local\Programs\Git\usr\bin\gpg.exe" (usou esse no caso)


+ configurar chave no terminal (LINUX)
git config --global user.signingkey BBBA9203FAF9DCA1
git config --global commit.gpgsign true
git config --global tag.gpgsign true


Criar variavel de ambiente para funcionar
Linux: export GPG_TTY=$(tty)

Ensinar o terminal a reconhecer o comando anterior
Linux: adicionar comando <export GPG_TTY=$(tty)> no .bash


EXTRA

+ mostrar informações da configuração global para verificar se os comandos foram realizados
git config --global --list


+ Commit sem verificação 
git commit -S -m "text commit"

+ add outro email na key

gpg --edit-key BBBA9203FAF9DCA1

terminal gpg > 
adduid
Realname e o email a ser alterado
uid 2
trust
decision = 5
save
