## Ansible for noobs

Playbook com roles do meu uso pessoal.

Nem tudo que uso na minha estação de trabalho foi configurado, [clique aqui pra ver a lista](todos.md) do que esta configurado ou vai ser em breve.

## Como usar

Configura o computador alvo no arquivo de configurações hosts.ini, exemplo:

``` ini
    [meu-pc]
    192.168.0.10
```

O arquivo playbook.yml possui variáveis de configuração que são utilizadas por algumas roles, então é interessante que coloque as suas informações.

``` yml
vars:
  nome: SEU_NOME
  email: SEU_EMAIL
  # GIST_ID utilizado pelo sync-settings do atom
  gistId: GIST_ID
  # key GPG
  signingkey: KEY_GPG
  # Token para acesso ao gist, recomendo usar uma token somente do gist
  # utilizado pelo sync-settings do atom
  personalAccessToken: COLOQUE_AQUI_SUA_TOKEN
```

Após realizar os ajustes, é só rodar o comando:

``` bash
    ansible-playbook playbook.yml -i hosts.ini --ask-become-pass
```
