---
title: "Surrealdb Pimeiros Passos"
linkTitle: "Primeiros passos"
date: 2022-11-16
description: >
  Primeiros passos com o banco de dados Surreladb, instalando e conectando.
---

## Instalação


### Docker

Se voce tem o docker e não deseja instalar diretamente na sua máquina de trabalho, instale o servidor através de um container docker, com o comando:

```ssh
docker run --rm -p 8000:8000 surrealdb/surrealdb:latest start
```

### Windows

A forma de instalar no windows é semelhante a forma de instação no linux, o equivalente ao `curl`, no windows é o comando [Invoke-WebRequest do PowerShell](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.3). O site do surreal indica o seguinte comando para instalação:

```ssh
iwr https://windows.surrealdb.com -useb | iex
```

Obs. Esse é um comando do [Powershell](https://learn.microsoft.com/pt-br/powershell/scripting/overview?view=powershell-7.3) e dependendo da versão, pode não funcionar da forma como está, se for o caso, tente trocar o `iwr` por `Invoke-WebRequest`.  

### macOS

A forma mais fácil é através do Homebrew, se voce não o tem instalado, siga as mesmas instruções para instalação no linux:

``` ssh
user@localhost % brew install surrealdb/tap/surreal
```

### Linux

A melhor forma de instalar em sistemas linux é através do comando `curl` :

``` ssh
curl -sSf https://install.surrealdb.com | sh
```

## Conectando

SurrealDB foi concebido para ser rápido e fácil, isso também se aplica a sua inicialização. Ainda não temos (no momento da escrita desse texto) um cliente GUI para iniciar e importar/exportar dados, mas isso não significa complexidade, na verdade é muito simples através da linha de comando.

### macOS/Linux

``` Bash
user@localhost % surreal start --log debug --user root --pass root memory
```

### Windows

``` Bash
PS C:\> surreal.exe start --log debug --user root --pass root memory
```

#### Output

Em qualquer um dos ambientes a saída resultante do comando deverá ser algo parecido com o apresentado abaixo:

``` Bash
[2022-07-28 15:50:34] INFO  surrealdb::iam Root authentication is enabled
[2022-07-28 15:50:34] INFO  surrealdb::dbs Database strict mode is disabled
[2022-07-28 15:50:34] INFO  surrealdb::kvs Starting kvs store in memory
[2022-07-28 15:50:34] INFO  surrealdb::kvs Started kvs store in memory
[2022-07-28 15:50:34] INFO  surrealdb::net Starting web server on 0.0.0.0:8000
[2022-07-28 15:50:34] INFO  surrealdb::net Started web server on 0.0.0.0:8000
```
