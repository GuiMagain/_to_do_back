# To-Do API com FastAPI e Docker Compose

Esta aplicação consiste em uma API RESTful desenvolvida com Python 3.11, FastAPI e SQLAlchemy para gerenciamento de tarefas, empacotada com Docker Compose e gerenciada via Poetry.

Para executar o projeto, é necessário ter o Git, o Docker e o Docker Compose instalados no sistema. Primeiramente, clone este repositório executando `git clone <URL_DO_SEU_REPOSITORIO>` e acesse o diretório do projeto com `cd _to_do_back`.

As variáveis de ambiente padrão já vêm definidas diretamente no arquivo `docker-compose.yml` (`DATABASE_URL="sqlite:///.to_do.db"`, `MEU_USUARIO="admin"`, `MINHA_SENHA="12345678"` e `PYTHONUNBUFFERED=1`). Caso deseje customizá-las localmente com um arquivo próprio, utilize o modelo de exemplo executando `cp .env.example .env`.

Para construir a imagem Docker e iniciar os contêineres em segundo plano, execute exatamente o comando:
`docker-compose up --build -d`

Caso queira acompanhar a saída e os logs do contêiner em tempo real, execute:
`docker-compose logs -f app`

Com a aplicação em execução, acesse a documentação interativa da API no navegador pelo Swagger UI em `http://localhost:8000/docs` ou pelo ReDoc em `http://localhost:8000/redoc`. As rotas exigem autenticação HTTP Basic; ao realizar requisições ou clicar em Authorize no Swagger, utilize o usuário `admin` e a senha `12345678`.

Para encerrar a aplicação e parar os contêineres, execute exatamente o comando:
`docker-compose down`