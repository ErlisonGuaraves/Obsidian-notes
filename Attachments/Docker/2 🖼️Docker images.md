
Até agora, temos aceitado que as <mark style="background: #ABF7F7A6;">imagens</mark> são uma receita para criar um container, mas efetivamente como elas funcionam?

Uma imagem nada mais é que um conjunto de camadas, que ao serem unidas formam imagens. E essas camadas são independentes, cada uma tem o seu respectivo ID (identificador).

Vamos voltar para o terminal no caso do `dockersamples` para visualizar esse exemplo.

Após executar um `docker pull` do `dockersamples` e um `docker run` na nossa imagem, podemos visualizar as imagens que temos baixadas no nosso sistema, através do comando `docker images` ou `docker image ls`.

```bash
docker images
```

Podemos ir um pouco mais além, podemos dar o comando `docker inspect` em uma imagem passando o identificador do que queremos inspecionar.

```bash
docker inspect <id_da_imagem>
```

Existe um comando específico para verificar quais são as camadas de uma imagem. Basta usar o comando `docker history`, passando o ID da imagem.

```bash
docker history <id_da_imagem>
```

Vimos como podemos utilizar variáveis em nossas imagens e containers através das instruções `ARG` e `ENV`.  Qual é a diferença entre elas?

A instrução ARG define variáveis que são utilizadas durante o processo de build da imagem, ou seja, quando a imagem do container está sendo criada. Já a instrução ENV define variáveis que serão utilizadas dentro do container em tempo de execução, quando a aplicação está sendo executada.

## bind mount

O bind mount no Docker permite montar diretórios ou arquivos do sistema de arquivos do host dentro de um contêiner, permitindo que o contêiner acesse e interaja diretamente com esses arquivos. Isso é útil em várias situações.

Como criar um bind mount com a sintaxe correta?

```bash
docker run -d -v /caminho/no/host:/caminho/no/container <nome_da_imagem>
```

Mas qual é a vantagem de usar volumes ao invés dos bind mounts?


[3 🖥️ Comandos uteis](3%20🖥️%20Comandos%20uteis.md)