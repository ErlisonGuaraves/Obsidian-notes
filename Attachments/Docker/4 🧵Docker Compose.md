
Docker Compose é uma ferramenta poderosa que permite definir e gerenciar aplicações multi-contêineres. Com um único arquivo YAML, você pode especificar todos os serviços necessários para a sua aplicação, incluindo suas configurações e dependências. Isso facilita a orquestração e o gerenciamento de ambientes de desenvolvimento, teste e produção, garantindo que todos os componentes da aplicação funcionem harmoniosamente.

### Aplicação Web Simples com Nginx e Redis

```yaml
version: '3'
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
  redis:
    image: redis:latest

```

### Aplicação com Node.js e MongoDB

Este exemplo configura uma aplicação Node.js que se conecta a um banco de dados MongoDB.

```yaml
version: '3'
services:
  app:
    image: node:14
    working_dir: /app
    volumes:
      - .:/app
    command: npm start
    ports:
      - "3000:3000"
    depends_on:
      - db
  db:
    image: mongo:latest
    ports:
      - "27017:27017"
    volumes:
      - mongo-data:/data/db

volumes:
  mongo-data:

```

### Aplicação com PostgreSQL e PgAdmin

Este exemplo configura um banco de dados PostgreSQL e uma interface de administração PgAdmin.

```yaml
version: '3'
services:
  db:
    image: postgres:latest
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: mydb
    volumes:
      - pgdata:/var/lib/postgresql/data
    ports:
      - "5432:5432"
  pgadmin:
    image: dpage/pgadmin4
    environment:
      PGADMIN_DEFAULT_EMAIL: admin@example.com
      PGADMIN_DEFAULT_PASSWORD: admin
    ports:
      - "8080:80"
    depends_on:
      - db

volumes:
  pgdata:

```

Estes exemplos mostram como usar Docker Compose para configurar diferentes serviços e suas dependências de forma simples e eficiente.