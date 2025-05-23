# Configurando o Ambiente Local para o Violin Lessons API

Este guia descreve como configurar o ambiente local, compilar, executar e testar o projeto Violin Lessons API, uma aplicação Ruby on Rails.

## Configurando o Ambiente Local

### Pré-requisitos

Certifique-se de ter os seguintes softwares instalados:

- [Ruby](https://www.ruby-lang.org/)
- [Rails](https://rubyonrails.org/)
- [PostgreSQL](https://www.postgresql.org/)

### Passos para Configuração

1. **Clone o Repositório**

   ```bash
   git clone https://github.com/your-username/violin_lessons_api.git
   cd violin_lessons_api
   ```

2. **Instale as Dependências**

   ```bash
   bundle install
   ```

3. **Configure o Banco de Dados**

   - Copie o arquivo de exemplo de configuração do banco de dados:
     ```bash
     cp config/database.yml.example config/database.yml
     ```
   - Atualize o arquivo `config/database.yml` com as credenciais do seu banco de dados local.
   - Crie e migre o banco de dados:
     ```bash
     rails db:create
     rails db:migrate
     ```

4. **(Opcional) Popule o Banco de Dados**

   ```bash
   rails db:seed
   ```

## Compilando e Subindo o Projeto

1. **Inicie o Servidor**

   ```bash
   rails server
   ```

2. Acesse a aplicação em `http://localhost:3000`.

## Testando o Projeto

- **Executar Testes Automatizados**

  ```bash
  rails test
  ```

- **Limpar e Reconfigurar o Banco de Dados para Testes**

  ```bash
  rails db:reset
  ```

## Verificando a Documentação Aberta (Open Doc)

Se o projeto incluir documentação aberta, você pode verificá-la seguindo os passos abaixo:

1. Certifique-se de que o servidor está em execução.
2. Acesse a URL da documentação (por exemplo, `http://localhost:3000/docs`) no navegador.

## Solução de Problemas

- Verifique se o PostgreSQL está em execução.
- Confirme se as versões do Ruby e Rails são compatíveis com o projeto.
- Caso encontre problemas de permissão, tente executar os comandos com `sudo`.

## Usando Docker e Docker Compose

Se preferir, você pode usar o Docker para configurar e executar o projeto. Certifique-se de ter o [Docker](https://www.docker.com/) e o [Docker Compose](https://docs.docker.com/compose/) instalados.

### Passos para Configuração com Docker

1. **Construa os Contêineres**

   No diretório raiz do projeto, execute:

   ```bash
   docker-compose build
   ```

2. **Inicie os Contêineres**

   Suba os serviços definidos no `docker-compose.yml`:

   ```bash
   docker-compose up
   ```

3. **Acesse a Aplicação**

   A aplicação estará disponível em `http://localhost:3000`.

### Comandos Úteis

- **Executar Migrações no Banco de Dados**

  ```bash
  docker-compose run web rails db:migrate
  ```

- **Popule o Banco de Dados**

  ```bash
  docker-compose run web rails db:seed
  ```

- **Executar Testes**

  ```bash
  docker-compose run web rails test
  ```

- **Parar os Contêineres**

  ```bash
  docker-compose down
  ```

### Solução de Problemas com Docker

- Certifique-se de que as portas necessárias (como `3000` para o servidor e `5432` para o PostgreSQL) estão disponíveis.
- Verifique os logs dos contêineres para identificar possíveis erros:

  ```bash
  docker-compose logs
  ```

- Caso precise reconstruir os contêineres, execute:

  ```bash
  docker-compose build --no-cache
  ```

## Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).
