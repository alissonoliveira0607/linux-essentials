# Curso de Linux Essentials

## Introdução ao Linux
- [O que é o Linux?](https://4linux.com.br/o-que-e-linux/)
- [História do Linux](https://www.google.com/search?q=historia+do+linux&rlz=1C1RXQR_enBR1088BR1088&oq=histor&gs_lcrp=EgZjaHJvbWUqDAgAEAAYQxiABBiKBTIMCAAQABhDGIAEGIoFMgYIARBFGDkyDQgCEAAYgwEYsQMYgAQyCQgDEAAYAxjJAzINCAQQABiSAxiABBiKBTIGCAUQRRg8MgYIBhBFGDwyBggHEEUYPNIBCDIwMjFqMGo0qAIAsAIA&sourceid=chrome&ie=UTF-8)
- [Distribuições Linux](https://pt.wikipedia.org/wiki/Distribui%C3%A7%C3%A3o_Linux)
- [Por que usar Linux?](https://blog.4linux.com.br/linux-para-usuarios-comuns/#:~:text=O%20Linux%20%C3%A9%20conhecido%20por,gastar%20dinheiro%20com%20hardware%20novo.)

## Ambiente Linux
- Interface de linha de comando (CLI)
## O melhor amigo do sysadmin
  - `man`
    - **Obter detalhamentos sobre comandos usando `man`**
      ```bash
      man <comand>
      ```

## Comandos Básicos
- Manipulação de arquivos e diretórios
  - `ls`, `cd`, `mkdir`, `rm`, `cp`, `mv`
    - **Exemplo: Listar todos os arquivos na pasta atual usando `ls`**
      ```bash
      ls
      ```
    - **Exemplo: Navegar até a pasta "Documentos" usando `cd`**
      ```bash
      cd <diretório>
      ```
    - **Exemplo: Criar uma nova pasta chamada "exemplo" usando `mkdir`**
      ```bash
      mkdir exemplo
      ```
    - **Exemplo: Remover um arquivo usando `rm`**
      ```bash
      rm <arquivo>
      ```      
    - **Exemplo: Remover diretórios e subdiretórios usando `rm -rf`**
      ```bash
      rm -rf <diretório>
      ```  
    - **Exemplo: Copiar arquivos `cp`**
      ```bash
      cp <arquivo>
      ```      
    - **Exemplo: Copiar arquivos de forma recursiva `cp -r`**
      ```bash
      cp -r <diretório/arquivo>
      ```      
## Visualizar / ler conteúdo      
- Visualização de conteúdo de arquivos
  - `cat`, `less`, `head`, `tail`
    - **Exemplo: Visualizar o conteúdo de um arquivo de texto com `cat`**
      ```bash
      cat arquivo.txt
      ```
    - **Exemplo: Visualizar as primeiras linhas de um arquivo com `head`**
      ```bash
      head arquivo.txt
      ```
    - **Exemplo: Visualizar as últimas linhas de um arquivo com `tail`**
      ```bash
      tail arquivo.txt
      ```
    - **Exemplo: Visualizar as últimas linhas de um arquivo com `less`**
      ```bash
      less arquivo.txt
      ```
## Consultar arquivos
- Comandos de busca
  - `grep`, `find`
    - **Exemplo: Procurar por um padrão em um arquivo usando `grep`**
      ```bash
      grep "padrão" arquivo.txt
      ```
    - **Exemplo: Procurar por arquivos por nome usando `find`**
      ```bash
      find /diretorio -name "nome_arquivo"
      ```
    - **Exemplo: Procurar por arquivos modificados recentemente usando `find`**
      ```bash
      find /diretorio -mtime -1
      ```

## Administração de Usuários e Grupos
- Gerenciamento de usuários
  - `adduser`, `usermod`, `passwd`, `userdel`
    - **Exemplo: Adicionar um novo usuário ao sistema com `adduser`**
      ```bash
      adduser novo_usuario
      ```
    - **Exemplo: Modificar as configurações de um usuário com `usermod`**
      ```bash
      usermod -c "Novo nome" nome_usuario
      ```
    - **Exemplo: Alterar a senha de um usuário com `passwd`**
      ```bash
      passwd nome_usuario
      ```
    - **Exemplo: Remover usuário com `userdel`**
      ```bash
      userdel --remove-all-files <user>
      ```

- Gerenciamento de grupos
  - `groupadd`, `groupmod`, `groupdel`
    - **Exemplo: Criar um novo grupo chamado "developers" com `groupadd`**
      ```bash
      groupadd developers
      ```
    - **Exemplo: Modificar as configurações de um grupo com `groupmod`**
      ```bash
      groupmod -n novo_nome_grupo nome_grupo
      ```
    - **Exemplo: Remover um grupo existente com `groupdel`**
      ```bash
      groupdel nome_grupo
      ```

## Permissões de Arquivos

- Propriedades de arquivos
- Permissões básicas
- Alterando permissões
Permissões no Linux

### Permissões em Forma de Letras:

```
r = Permissão de Leitura (Read): Permite visualizar o conteúdo do arquivo.
w = Permissão de Escrita (Write): Permite modificar ou deletar o arquivo.
x = Permissão de Execução (Execute): Permite executar o arquivo se for um programa ou script.
```

### Permissões em Forma de Números:

```
0 = Nenhuma permissão (---): Nenhuma permissão concedida.
1 = Executar apenas (--x): Permite apenas a execução do arquivo.
2 = Escrever apenas (-w-): Permite apenas a modificação do arquivo.
3 = Escrever e Executar (-wx): Permite a modificação e execução do arquivo.
4 = Ler apenas (r--): Permite apenas visualizar o conteúdo do arquivo.
5 = Ler e Executar (r-x): Permite visualizar e executar o arquivo.
6 = Ler e Escrever (rw-): Permite visualizar e modificar o conteúdo do arquivo.
7 = Ler, Escrever e Executar (rwx): Permite todas as operações no arquivo.
```

### Permissões especiais suid bit:

```
s (setuid): Ao definido em um arquivo, permite que um usuário execute o arquivo com os privilégios do proprietário do arquivo, em vez de seus próprios privilégios.
s (setgid): Ao definido em um arquivo, permite que um usuário execute o arquivo com os privilégios do grupo proprietário do arquivo, em vez de seus próprios privilégios.
t (sticky bit): Ao definido em um diretório, impede que usuários que não sejam o proprietário do arquivo excluam ou renomeiem arquivos dentro desse diretório, mesmo que tenham permissão de escrita no diretório.
```

### Exemplos de Combinando Permissões em Forma de Letras:

```
- rw- = Leitura e Escrita (No Executar)
- rwx = Leitura, Escrita e Execução
- r-x = Leitura e Execução (No Escrever)
```

### Exemplos de Combinando Permissões em Forma de Números:

```
0 = Nenhuma permissão (---)
1 = Executar apenas (--x)
2 = Escrever apenas (-w-)
3 = Escrever e Executar (-wx)
4 = Ler apenas (r--)
5 = Ler e Executar (r-x)
6 = Ler e Escrever (rw-)
7 = Ler, Escrever e Executar (rwx)
```

### Exemplos de permissões especiais suid bit:

```
s (setuid)
s (setgid)
t (sticky bit)
```

- `chmod`
  - **Exemplo: Alterar as permissões de um arquivo para que todos possam ler e escrever usando `chmod`**
    ```bash
    chmod ugo+rw arquivo.txt
    ```

  - **Exemplo: Remover permissões de escrita de um arquivo usando `chmod`**
    ```bash
    chmod go-w arquivo.txt
    ```

  - **Exemplo: Restaurar permissões padrão de um arquivo usando `chmod`**
    ```bash
    chmod 644 arquivo.txt
    ```

## Processos
- Monitoramento e gerenciamento de processos
  - `ps`, `top`, `kill`
    - **Exemplo: Listar todos os processos em execução com `ps`**
      ```bash
      ps aux
      ```
    - **Exemplo: Monitorar os processos em tempo real com `top`**
      ```bash
      top
      ```
    - **Exemplo: Encerrar um processo específico com `kill`**
      ```bash
      kill PID
      ```

## Redes no Linux
- Comandos de rede
  - `ifconfig`, `ping`, `traceroute`, `netstat`
    - **Exemplo: Verificar as configurações de rede com `ifconfig`**
      ```bash
      ifconfig
      ```
    - **Exemplo: Verificar a conectividade com um servidor usando `ping`**
      ```bash
      ping servidor.com
      ```
    - **Exemplo: Exibir as conexões de rede ativas com `netstat`**
      ```bash
      netstat -tuln
      ```

## Serviços e Daemon
- Gerenciamento de serviços
  - `systemctl`
    - **Exemplo: Iniciar, parar e reiniciar o serviço SSH com `systemctl`**
      ```bash
      systemctl start ssh
      systemctl stop ssh
      systemctl restart ssh
      ```
    - **Exemplo: Verificar o status de um serviço com `systemctl status`**
      ```bash
      systemctl status ssh
      ```
    - **Exemplo: Habilitar um serviço para iniciar na inicialização com `systemctl enable`**
      ```bash
      systemctl enable ssh
      ```

## Armazenamento de Dados
- Montagem de dispositivos de armazenamento
  - `mount`, `umount`
    - **Exemplo: Montar uma unidade USB com `mount`**
      ```bash
      mount /dev/sdb1 /mnt/usb
      ```
    - **Exemplo: Desmontar uma unidade USB com `umount`**
      ```bash
      umount /mnt/usb
      ```
    - **Exemplo: Verificar as unidades montadas com `mount`**
      ```bash
      mount
      ```

## Backup e Restauração
- Ferramentas de backup
  - `tar`, `rsync`
    - **Exemplo: Criar um arquivo de backup com `tar`**
      ```bash
      tar -cvf backup.tar /diretorio
      ```
    - **Exemplo: Sincronizar diretórios entre dois locais com `rsync`**
      ```bash
      rsync -avz /origem /destino
      ```
    - **Exemplo: Extrair o conteúdo de um arquivo de backup com `tar`**
      ```bash
      tar -xvf backup.tar
      ```

## Segurança
- Firewall no Linux
  - `iptables`
    - **Exemplo: Configurar uma regra de firewall para bloquear tráfego de entrada com `iptables`**
      ```bash
      iptables -A INPUT -s IP_Da_Fonte -j DROP
      ```
    - **Exemplo: Exibir as regras de firewall atuais com `iptables -L`**
      ```bash
      iptables -L
      ```
    - **Exemplo: Remover uma regra de firewall com `iptables -D`**
      ```bash
      iptables -D INPUT numero_regra
      ```




