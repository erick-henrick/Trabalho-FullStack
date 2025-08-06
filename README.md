Sistema de Gestão de Petshop
Este é um projeto Fullstack para um sistema de gestão de petshop, permitindo o gerenciamento de tutores, pets, serviços e solicitações de agendamento. A arquitetura é baseada em um Backend-for-Frontend (BFF) que renderiza as páginas e consome uma API REST principal para as regras de negócio e acesso ao banco de dados.

✨ Funcionalidades Principais
Autenticação de Usuários: Sistema de login com sessões e autenticação baseada em Token JWT para comunicação com o backend.

Gestão de Tutores: CRUD (Criar, Ler, Atualizar, Deletar) de tutores de pets.

Gestão de Pets: CRUD de pets, associados aos seus respectivos tutores.

Gestão de Serviços: CRUD de serviços oferecidos pelo petshop, incluindo nome e preço.

Gestão de Produtos: CRUD de produtos.

Gestão de Solicitações: Funcionalidade principal para agendar serviços para um ou mais pets de um tutor, com data, hora e status (Agendado, Em Andamento, Concluído, Cancelado).

Interface Administrativa: Páginas dinâmicas para visualizar e interagir com os dados em tabelas, formulários e modais.

🏗️ Arquitetura
O projeto utiliza uma arquitetura desacoplada, onde o frontend (renderizado no servidor) e o backend (API de negócio) são aplicações distintas.

┌─────────────┐     ┌──────────────────────────────────┐      ┌─────────────────────────┐
│             │     │      Backend-for-Frontend (BFF)    │      │                         │
│  Navegador  │<───>│         (Este Projeto)             │<────>│  Backend Principal      │
│   (Client)  │     │  - Express.js                      │      │   (API REST)            │
│             │     │  - Renderização com EJS            │      │  - Lógica de Negócio    │
└─────────────┘     │  - Gerencia Sessões                │      │  - Acesso ao Banco de Dados │
                    │  - Atua como Proxy para o Backend  │      │                         │
                    └──────────────────────────────────┘      └─────────────────────────┘
🛠️ Tecnologias Utilizadas
Backend-for-Frontend (BFF) - Pasta frontend
Node.js: Ambiente de execução JavaScript.

Express.js: Framework web para criar o servidor e as rotas.

EJS (Embedded JavaScript): Template engine para renderizar as páginas HTML dinamicamente.

express-session: Para gerenciamento de sessões de usuário.

node-fetch: Para fazer requisições HTTP do BFF para o Backend Principal.

dotenv: Para gerenciar variáveis de ambiente.

Nodemon: Para reiniciar o servidor automaticamente durante o desenvolvimento.

Frontend (Client-Side)
Materialize CSS: Framework de CSS para estilização e componentes (formulários, modais, tabela).

IMask.js: Biblioteca para criar máscaras de input (ex: data e hora).

JavaScript (Vanilla): Para interatividade da página, como chamadas fetch para o BFF, manipulação do DOM e eventos.

Backend Principal (API)
Tecnologia não especificada, pode ser qualquer framework que exponha uma API REST, como Node.js/Express, Spring Boot, Django, etc.

Autenticação: JWT (JSON Web Tokens).

Banco de Dados
Qualquer banco de dados relacional (PostgreSQL, MySQL) ou não-relacional (MongoDB) suportado pelo Backend Principal.

🚀 Como Iniciar o Projeto
Siga os passos abaixo para configurar e rodar a aplicação em seu ambiente local.

Pré-requisitos
Node.js (versão 16 ou superior)

NPM ou Yarn

Git

Instalação
Clone o repositório:

Bash

git clone https://URL_DO_SEU_REPOSITORIO.git
cd nome-da-pasta-do-projeto
Configure as Variáveis de Ambiente:
Este projeto (o BFF) precisa de um arquivo .env na raiz da pasta frontend. Crie um arquivo chamado .env e adicione as seguintes variáveis:

Ini, TOML

# .env

# URL base da sua API do Backend Principal
BACK_URL=http://localhost:8080/api

# Segredo para a sessão do Express (use uma string longa e aleatória)
SESSION_SECRET=meu_segredo_super_secreto_para_a_sessao

# Porta em que o BFF irá rodar
PORT=3000
No seu app.js, ajuste a linha da sessão para usar process.env.SESSION_SECRET em vez de process.env.TOKEN.

Instale as dependências do Backend-for-Frontend:

Bash

cd frontend  # Navegue para a pasta do BFF
npm install
Instale as dependências do Backend Principal:
Siga as instruções específicas do seu outro projeto de backend para instalá-lo.

Executando a Aplicação
Para que tudo funcione, você precisa rodar os dois servidores (o Backend Principal e o BFF).

Inicie o Backend Principal:
No terminal do seu projeto de backend, inicie o servidor (o comando pode variar).

Bash

# Exemplo:
npm start
Certifique-se de que ele esteja rodando na URL especificada em BACK_URL (ex: http://localhost:8080).

Inicie o Backend-for-Frontend (este projeto):
No terminal da pasta frontend deste projeto, execute:

Bash

# Para desenvolvimento (reinicia automaticamente com nodemon)
npm run dev

# Ou para produção
npm start
Certifique-se de que seu package.json tem esses scripts definidos.

Acesse a aplicação:
Abra seu navegador e acesse http://localhost:3000 (ou a porta que você definiu).

📄 Endpoints do BFF (Backend-for-Frontend)
A seguir, uma visão geral das principais rotas definidas em /routes/solicitations.js.

GET /solicitations: Renderiza a página principal de gestão de solicitações, buscando todos os dados necessários (solicitações, tutores, serviços).

POST /solicitations: Recebe os dados do formulário de nova solicitação, faz o proxy e envia para o endpoint POST do backend principal.

GET /solicitations/fetch-pets-for-tutor/:tutorId: Rota auxiliar para popular o seletor de pets dinamicamente.

GET /solicitations/:id: Busca os dados de uma solicitação específica para preencher o formulário de edição.

PUT /solicitations/:id: Recebe os dados do formulário de edição e os envia para o endpoint PUT do backend principal.

DELETE /solicitations/:id: Recebe uma requisição de exclusão e a envia para o endpoint DELETE do backend principal.
