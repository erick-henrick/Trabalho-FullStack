# Portfólio — Trabalho FullStack

Projeto convertido para servir como portfólio pessoal. Este repositório contém uma aplicação web construída com Node.js + EJS (templates), JavaScript e CSS, criada originalmente como trabalho da disciplina de FullStack na faculdade Nova Roma.

## Visão geral
Uma aplicação simples para exibir informações pessoais, projetos e contato. Ideal para personalizar com seu nome, bio, lista de projetos e links (GitHub, LinkedIn, etc.).

## Tecnologias
- Node.js
- EJS (templates)
- JavaScript (client & server)
- CSS
- HTML

(Conforme a composição do repositório: EJS ~48%, JavaScript ~44%.)

## Estrutura sugerida do projeto
- /views — templates EJS (páginas, partials like header/footer)
- /public — arquivos estáticos (CSS, imagens, JS do cliente)
- /routes — rotas Express (se existir)
- server.js / app.js — ponto de entrada da aplicação
- package.json — scripts e dependências

A estrutura exata pode variar; personalize conforme seu código.

## Como usar localmente

1. Clone o repositório
   git clone https://github.com/erick-henrick/Trabalho-FullStack.git
2. Entre na pasta do projeto
   cd Trabalho-FullStack
3. Instale dependências
   npm install
4. Execute a aplicação
   - Para produção (se existir script):
     npm start
   - Para desenvolvimento com reinício automático (se houver nodemon):
     npm run dev

5. Abra no navegador
   Acesse http://localhost:3000 (ou a porta configurada em PORT)

Observação: se sua aplicação usa outro arquivo de entrada ou script, ajuste os comandos acima conforme o package.json do projeto.

## Como personalizar para seu portfólio
- Substitua o texto de apresentação (nome, bio) nos arquivos em /views (por exemplo, views/index.ejs ou views/partials/header.ejs).
- Atualize a seção de projetos: adicione cards com título, descrição, tecnologias, imagem e link para repo/demonstração.
- Ajuste estilos em /public/css para combinar com sua identidade visual.
- Adicione uma rota/endpoint para exibir detalhes de cada projeto, se desejar.

## Deploy (sugestões rápidas)
- Vercel: ideal para front-ends; para apps Node/Express prefira uma configuração de serverless ou usar uma plataforma que suporte Node.
- Render / Heroku: suportam Node.js facilmente. Configure variável PORT e faça o deploy a partir do repositório GitHub.
- GitHub Pages: apenas para front-ends estáticos (é necessário gerar um build estático se você transformar as views em HTML estático).

## Boas práticas para um portfólio
- Inclua uma seção "Sobre" com uma foto profissional e uma curta biografia.
- Mostre 4–8 projetos relevantes com links para o código e, quando possível, a demo ao vivo.
- Destaque tecnologias usadas e seu papel em cada projeto.
- Mantenha o design limpo e responsivo (mobile-first).

## Contribuição
Se alguém quiser contribuir, abra uma issue ou um pull request descrevendo as mudanças propostas.

## Licença
Escolha uma licença (por exemplo, MIT) e adicione um arquivo LICENSE se desejar permitir reuso.

## Contato
Seu Nome — erickhenrick629@gmail.com 
Link: https://github.com/erick-henrick
