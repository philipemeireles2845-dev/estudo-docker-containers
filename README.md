# Estudo Docker - Containers

## Sobre
Este repositório documenta meu aprendizado sobre Docker e containerização.

**Autor:** [Philipe Emanuel de Souza Meireles]
**Curso:** [Segurança Cibernética]
**Disciplina:** [Banco de Dados]
**Data:** [06/10/2026]

## O que estou aprendendo
- Conceitos fundamentais do Docker
- Como criar e gerenciar containers
- Trabalhar com imagens Docker
- Configurar bancos de dados em containers
- Usar Docker Compose para aplicações multi-container

## Estrutura do Projeto
- `containers/` - Dockerfiles e configurações de containers
- `compose/` - Arquivos docker-compose.yml
- `scripts/` - Scripts de configuração e inicialização
- `README.md` - Este arquivo de documentação

## Status do Estudo
- [x] Tarefa 1 - Primeiro container
- [x] Tarefa 2 - Container personalizado
- [x] Tarefa 3 - Banco de dados
- [ ] Tarefa 4 - Docker Compose (Problema na conexão entre o banco de dados e a aplicação)
- [ ] Tarefa 5 - Aplicação completa

1- Qual a principal vantagem de usar containers com Docker em vez de instalar um banco de dados e um servidor web diretamente em sua máquina?
Isolamento de ambiente. Cada aplicação roda separada, sem poluir o sistema operacional nem gerar conflitos de versões (ex: precisar de duas versões do PHP na mesma máquina). Além disso, elimina o problema do "na minha máquina funciona".

2- Explique com suas palavras o propósito de um Dockerfile. Por que ele é tão importante para a reprodutibilidade de ambientes?
O Dockerfile é o projeto ("receita") para criar uma imagem do Docker. Ele é crucial porque garante que a aplicação rode exatamente da mesma forma em qualquer computador ou servidor, sem depender de configurações manuais.

3- Em que cenário o Docker Compose se torna essencial? Por que não usar apenas comandos múltiplos docker run?
Ele é essencial quando a aplicação usa múltiplos serviços (ex: backend, banco de dados e servidor web).
 Não usamos vários composes run porque o compose centraliza tudo em um único arquivo, conecta os containers em rede automaticamente e permite subir ou desligar todo o ecossistema com um só comando (docker compose up).

4- Qual a importância dos volumes do Docker (como o que usamos para o banco de dados MySQL)? O que aconteceria com os dados se não usássemos um volume?
Volumes servem para salvar dados de forma permanente. Sem volume: como os containers são temporários, ao desligar ou deletar o container do MySQL, todos os dados do banco seriam apagados para sempre. O volume salva esses dados na sua máquina física.

5- Como o uso de containers pode facilitar o trabalho da equipe em um projeto de desenvolvimento de software?
Entrada rápida de novos membros: basta baixar o projeto e rodar um comando para ter o ambiente pronto.
Padronização: garante que todos os desenvolvedores (e o servidor de produção) usem o mesmo ambiente, evitando bugs por diferença de configuração.