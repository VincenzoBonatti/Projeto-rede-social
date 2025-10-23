# Projeto Rede Social

Este repositório contém o código-fonte de uma aplicação de rede social, construída com uma arquitetura moderna e desacoplada, utilizando React, Docker e serviços de nuvem como Azure e MongoDB Atlas.

## 🏛️ Arquitetura da Aplicação

A arquitetura do projeto foi planejada para ser escalável e de fácil manutenção, separando as responsabilidades do frontend, backend e serviços de dados. O diagrama abaixo ilustra o fluxo principal e as tecnologias utilizadas:

(Lembre-se de fazer o upload do seu diagrama para o repositório e atualizar o caminho da imagem acima).

### Pilha de Tecnologia (Tech Stack)

A aplicação é dividida nos seguintes componentes principais:

  * *Frontend (Cliente):*

      * *Tecnologia:* React.js (JavaScript)
      * *Descrição:* É a interface com o usuário, executada no navegador (navegador). É responsável por todas as telas, incluindo o fluxo de cadastro/login.
      * *Deploy:* A aplicação React é containerizada com Docker e hospedada na plataforma Render.

  * *Backend (Servidor):*

      * *Tecnologia:* API (ex: Node.js, C\#, Python) documentada com Swagger.
      * *Descrição:* O cérebro da aplicação. É uma API RESTful que centraliza todas as regras de negócio e se comunica com os serviços de dados.
      * *Deploy:* A API também é containerizada com Docker, o que permite que ela seja hospedada em qualquer ambiente compatível (como Render, AWS, Azure, etc.).

  * *Serviços de Nuvem (Dados):*

      * *Banco de Dados:* MongoDB Atlas
          * *Propósito:* Armazena os dados principais da aplicação, como dados do usuário, postagens, comentários, etc.
      * *Armazenamento de Mídia:* Azure Blob Storage
          * *Propósito:* Usado para armazenar imagens e outros arquivos de mídia que os usuários fazem upload, mantendo o custo de armazenamento baixo e o acesso rápido.

## ✨ Funcionalidades Principais

  * 🔐 *Autenticação:* Cadastro e Login de usuários.
  * 🧑‍💻 *Gerenciamento de Usuários:* Armazenamento de dados de perfil no MongoDB.
  * 🖼️ *Upload de Mídia:* Envio e armazenamento de imagens de postagens no Azure Blob Storage.
  * 📖 *API Documentada:* Endpoints da API documentados com Swagger para fácil consulta e teste.
  * 🐳 *Containerização:* Aplicação 100% containerizada com Docker, facilitando o setup de desenvolvimento e o deploy em produção.

## 🚀 Como Executar (Getting Started)

Para executar este projeto localmente, você precisará ter o *Docker* e o *Docker Compose* instalados.

1.  *Clone o repositório:*

    bash
    git clone [URL_DO_SEU_REPOSITORIO]
    cd [NOME_DA_PASTA_DO_PROJETO]
    

2.  *Configurar Variáveis de Ambiente:*
    Este projeto precisa de chaves de API para se conectar aos serviços de nuvem. Renomeie os arquivos .env.example (se existirem) para .env dentro das pastas frontend e backend e preencha com suas credenciais:

    *Exemplo para backend/.env:*

    env
    # String de conexão do MongoDB Atlas
    MONGO_DB_CONNECTION_STRING="sua_string_de_conexao_aqui"

    # String de conexão do Azure Blob Storage
    AZURE_BLOB_STORAGE_CONNECTION_STRING="sua_string_de_conexao_aqui"
    

    *Exemplo para frontend/.env:*

    env
    # URL da sua API backend
    REACT_APP_API_URL="http://localhost:8080/api"
    

3.  *Subir os containers (Docker Compose):*
    Na raiz do projeto, execute o comando:

    bash
    docker-compose up -d --build
    

      * O docker-compose irá construir as imagens do frontend e backend e iniciar todos os serviços.

4.  *Acessar a aplicação:*

      * *Frontend (React):* http://localhost:3000
      * *Backend (Swagger):* http://localhost:8080/swagger

(Nota: As portas 3000 e 8080 são exemplos comuns. Ajuste conforme o seu arquivo docker-compose.yml)

## 🤝 Contribuição

Contribuições são bem-vindas\! Se você encontrar um bug ou tiver uma sugestão de melhoria, sinta-se à vontade para abrir uma *Issue* ou enviar um *Pull Request*.

## 📄 Licença

Este projeto é licenciado sob a licença [MIT / Apache 2.0 / etc.]. Veja o arquivo LICENSE para mais detalhes.
