# Desafio de Infraestrutura - BSN

Repositório contendo a infraestrutura automatizada, observabilidade e esteira de CI/CD para o projeto BookStack.

## 📂 Estrutura do Projeto
- **app-bookstack**: Aplicação principal e banco de dados.
- **monitoramento**: Configurações do Prometheus e métricas.
- **proxy**: Gerenciamento de domínios e SSL (Nginx Proxy Manager).
- **cicd**: Orquestração do GitLab e GitLab Runner.

## ⚙️ Como usar
1. Copie o arquivo `.env.example` para `.env` e preencha as variáveis.
2. Cada pasta contém seu próprio arquivo de orquestração Docker Compose.
