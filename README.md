# Boas-vindas ao repositório do projeto Docker Todo List!

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br/>

Neste projeto você irá:

1. **_Conteinerizar_** aplicações;
2. Criar uma conexão entre elas;
3. Orquestrar seu funcionamento.

Temos [uma aplicação full-stack](docker/todo-app) neste repositório: um **aplicativo de tarefas**! Esta aplicação precisa ser conteinerizada para funcionar. Você deverá desenvolver os arquivos de configuração para cada frente específica: `Front-end`, `Back-end` e, no nosso caso, para um aplicativo de `teste` que valida se as aplicações estão se comunicando.

---

Você deverá criar as imagens para as aplicações e configurar essas imagens com o `docker-compose`.

Para isto, você irá utilizar uma série de comandos do `docker` com diferentes níveis de complexidade.

Cada comando deverá ser escrito em seu próprio arquivo.

Para isto, siga os seguintes passos:

1. Leia o requisito e crie um arquivo chamado `commandN.dc` no diretório `docker-commands`, onde `N` é o número do requisito. Por exemplo:

    ```text
    Requisito 1: ./docker/docker-commands/command01.dc
    Requisito 2: ./docker/docker-commands/command02.dc
    Requisito 3: ./docker/docker-commands/command03.dc
    ```

    **⚠️ É muito importante que os seus arquivos tenham exatamente estes nomes! ⚠️**

2. Escreva neste arquivo o comando do CLI _(Interface de Linha de Comando)_ do Docker que resolve o requisito. Um exemplo de como vai ficar seu arquivo:

    ```dc
    docker network inspect bridge
    ```

---

Os arquivos principais do projeto estão na pasta `docker`, na raiz do projeto. Nela estão contidos:

1. Pasta `docker-commands`: onde ficarão os comandos exigidos pelos requisitos;
   - **⚠️ Importante: você deve assumir que essa é a pasta raiz para os comandos.**
   - Por exemplo, se você precisa referenciar um caminho em um comando, você deve assumir que sua pasta raiz esta partindo de `./docker`.
2. Pasta `todo-app`: onde fica a nossa **pseudo-aplicação**, que servirá como base para nossos `Dockerfile`s e `Compose`;
   - **⚠️ Essa aplicação conta com um [**README.md**](./docker/todo-app/README.md) próprio, que pode ser usado como referência na criação dos `dockerfiles` e do `docker-compose.yml`!**

Quando for necessário fazer a orquestração das aplicações, o arquivo `docker-compose.yml` deverá ser criado na pasta `./docker`. conforme o arquivo de exemplo [`docker/docker-compose.yml.example`](docker/docker-compose.yml.example).

</details>

# Orientações

<details>
  <summary><strong>‼️ Antes de começar a desenvolver</strong></summary><br/>

1. Instale as dependências:
  * `npm install`

</details>

<details>
<summary><strong> ⚠️ Configurações mínimas para execução do projeto</strong></summary><br />

Na sua máquina você deve ter:

 - Sistema Operacional Distribuição Unix
 - Node versão 16
 - Docker
 - Docker-compose versão >=1.29.2

➡️ O `node` deve ter versão igual ou superior à `16.14.0 LTS`:
  - Para instalar o nvm, [acesse esse link](https://github.com/nvm-sh/nvm#installing-and-updating);
  - Rode os comandos abaixo para instalar a versão correta de `node` e usá-la:
    - `nvm install 16.14 --lts`
    - `nvm use 16.14`
    - `nvm alias default 16.14`

➡️ O`docker-compose` deve ter versão igual ou superior à`ˆ1.29.2`:
  * Verifique no Course no dia `Orquestrando Containers com Docker Compose` como instalar corretamente.
  * Caso necessário, acesse o [link da documentação oficial com passos para desinstalar](https://docs.docker.com/compose/install/#uninstallation) a versão atualmente instalada.

</details>

# Requisitos obrigatórios do projeto

## Comandos docker

⚠ Lembre-se das instruções da seção [Entregáveis](#Entregáveis), especialmente no tópico `O que deverá ser desenvolvido`!

### 1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12`

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command01.dc`.

#### Observações técnicas

- O container **não deve ser inicializado**, somente criado;
- O container deve estar preparado para acesso interativo.

#### Dicas
- Dê uma olhada no comando [`create`](https://docs.docker.com/engine/reference/commandline/create/). 😉
- Lembre-se que um parâmetro não é necessariamente aplicável a apenas um comando;
- Consulte sempre que possível a [Documentação Oficial](https://docs.docker.com/engine/reference/commandline/docker/) sobre comandos básicos;
- Lembre-se que a esmagadora parte dos comandos docker recebe parâmetros (opções), como [nesse exemplo](https://docs.docker.com/engine/reference/commandline/logs/#options).

</details>

### 2. Inicie o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command02.dc`.

#### Observações técnicas

- O container `01container`, que acabou de ser criado e está parado, deve ser iniciado;
- Se o container tiver sido iniciado de modo interativo, ele deve se manter ativo ao iniciá-lo.
  
</details>

### 3. Liste os containers filtrando pelo nome `01container`

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command03.dc`.

#### Dicas

- Praticamente todo comando de listagem no Docker possui uma forma de filtragem.

</details>

### 4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command04.dc`.

#### Observações técnicas

- O container deve estar rodando e você deve ser capaz de **executar um comando** nesse container.

#### Dicas

- É possível fazer isso sem usar o comando `attach`.

</details>

### 5. Remova o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará os comandos nos arquivos `command05.dc` e `command03.dc`.

</details>

### 6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command06.dc`.

</details>

### 7. Rode um novo container com a imagem  `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command07.dc`.

</details>

### 8. Pare o container `02images` que está em andamento

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command08.dc`.

</details>

## Dockerfile

**⚠️ As aplicações a seguir contam com um [**README.md**](./docker/todo-app/README.md) próprio, que deve ser usado como referência na criação dos scripts!**

### 9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`

Escreva no arquivo `command09.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/back-end/Dockerfile`, esta imagem deve ter o nome `todobackend`.

No arquivo `./docker/todo-app/back-end/Dockerfile` escreva os comandos que farão com que a imagem:

- rode a partir da imagem do `node` na versão 16 alpine;
- exponha a porta 3001;
- defina o diretório de trabalho para `/app/back-end`
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `back-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/back-end/Dockerfile`);
- inicie a aplicação com o comando `npm start` respeitando as seguintes restrições:
  1. ao subir um container baseado na imagem buildada a partir desse Dockerfile, o comando `npm` deve ser rodado `sempre`;
  2. ao subir um container baseado na imagem buildada a partir desse Dockerfile, deve ser possível sobrescrever o comando `start`.

<details>
  <summary>➕ Informações adicionais</summary><br/>

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `back-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command09.dc`.

#### Dicas 

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

</details>

### 10. Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`

Escreva no arquivo `command10.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/front-end/Dockerfile`, esta imagem deve ter o nome `todofrontend`.

No arquivo `./docker/todo-app/front-end/Dockerfile` escreva os comandos que farão com que a imagem:

- rode a partir da imagem do `node` na versão 16 alpine;
- exponha a porta 3000;
- defina o diretório de trabalho para `/app/front-end`
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `front-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/front-end/Dockerfile`);
- inicie a aplicação com o comando `npm start` respeitando as seguintes restrições:
  1. ao subir um container baseado na imagem buildada a partir desse Dockerfile, o comando `npm` deve ser rodado `sempre`;
  2. ao subir um container baseado na imagem buildada a partir desse Dockerfile, deve ser possível sobrescrever o comando `start`.

<details>
  <summary>➕ Informações adicionais</summary><br/>

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/front-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `front-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command10.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

</details>

### 11. Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`

Escreva no arquivo `command11.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/tests/Dockerfile`, esta imagem deve ter o nome `todotests`.

No arquivo `./docker/todo-app/tests/Dockerfile` escreva os comandos que farão com que a imagem:

- rode a partir da imagem do `betrybe/puppetter:1.0`;
- defina o diretório de trabalho para `/app/tests`
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `tests` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/tests/Dockerfile`);
- inicie a aplicação com o comando `npm test` respeitando as seguintes restrições:
  1. ao subir um container baseado na imagem buildada a partir desse Dockerfile, o comando `npm` deve ser rodado `sempre`;
  2. ao subir um container baseado na imagem buildada a partir desse Dockerfile, deve ser possível sobrescrever o comando `test`.

<details>
  <summary>➕ Informações adicionais</summary><br/>

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `testes` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command11.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

#### Observações técnicas

- A aplicação `todotests` só funciona corretamente se estiver dockerizada e dentro de uma rede docker configurada corretamente.

</details>

# Requisito bônus do projeto

## Docker-compose

### 12. Suba uma orquestração em segundo plano com o docker-compose de forma que `backend`, `frontend` e `tests` consigam se comunicar

<details>
  <summary>➕ Informações adicionais</summary><br/>

O avaliador executará o comando no arquivo `command12.dc`. Este comando pressupõe a existência do arquivo `./docker/docker-compose.yml`.

O `docker-compose` deve rodar na versão 3 ou superior.

#### Dicas

- Use as imagens já **"buildadas"** que foram executadas nos requisitos 9, 10 e 11 para a criação do compose;
- Consulte a documentação em `./docker/todo-app/README.md`;
- É possível adicionar e extrair arquivos `.tar.gz` no `Dockerfile` com apenas um comando.

</details>
