

Aqui estão alguns dos comandos mais úteis do Docker que você pode utilizar para gerenciar contêineres:

**Listar contêineres em execução**:

```bash
docker ps
```

**Listar todos os contêineres (inclusive os parados)**:

```bash
docker ps -a
```

**Iniciar um contêiner**:

```bash
docker start <nome_da_imagem>
```

**Parar um contêiner**:

```bash
docker stop <nome_da_imagem>

```

**Remover um contêiner**:

```bash
docker rm <nome_da_imagem>

```

**Listar imagens de Docker**:

```bash
docker images
```

**Criar e iniciar um novo contêiner**:

```bash
docker run <nome_da_imagem>
```

**Executar um comando em um contêiner em execução**:

```bash
docker exec -it <nome_do_conteiner> <comando>

```

**Ver logs de um contêiner**:

```bash
docker logs <nome_do_conteiner>

```

Estes comandos são essenciais para quem está começando a trabalhar com Docker e precisa gerenciar contêineres de forma eficiente.

[🧵Docker Compose](🧵Docker%20Compose.md)