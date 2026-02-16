# Desafio de Infraestrutura - BSN

Este repositório contém a orquestração completa da infraestrutura, monitoramento e esteira de CI/CD para o projeto **BookStack**. O objetivo é garantir um ambiente resiliente, automatizado e com alta disponibilidade para a gestão de documentação técnica.

---

### 📂 1. Estrutura do Projeto

O projeto utiliza uma arquitetura modular baseada em containers Docker, facilitando a manutenção e o isolamento de falhas:

* **`app-bookstack`**: Core da aplicação (PHP/Laravel) e banco de dados relacional (MariaDB).
* **`proxy`**: Camada de borda para gerenciamento de tráfego, domínios e certificados SSL (Nginx Proxy Manager).
* **`monitoramento`**: Stack de observabilidade para coleta de métricas de infraestrutura (Prometheus).
* **`cicd`**: Orquestração de automação e deploy contínuo (GitLab Self-Hosted e GitLab Runner).

---

### ⚙️ 2. Instruções de Instalação

Siga os passos abaixo para implantar o ambiente em seu servidor local ou VPS:

1. **Configuração de Variáveis:**
   Crie o seu arquivo de ambiente com base no modelo fornecido:
   ```bash
   cp .env.example .env
Provisionamento da Rede:
É obrigatório criar a rede global para que os containers de diferentes módulos se comuniquem:

Bash
docker network create proxy-nw
Deploy dos Módulos:
Navegue até o diretório de cada serviço e inicie a stack:

Bash
docker-compose up -d

🔗 3. Documentação
Consulte os manuais oficiais para configurações avançadas e suporte técnico:

📘 Manual Oficial do BookStack

🛠️ Guia de Comandos Artisan (CLI)

🐳 Documentação da Imagem (LinuxServer.io)

📊 Documentação do Prometheus

🦊 GitLab Docker Guide

🛡️ 4. Segurança e Boas Práticas
Persistência de Dados: Todos os volumes estão mapeados para garantir a integridade dos dados e das documentações em caso de reinicialização.

SSL/TLS: O gerenciamento é centralizado no Nginx Proxy Manager com renovação automática via Let's Encrypt.

Git Hygiene: O arquivo .env contém credenciais sensíveis e está configurado para ser ignorado pelo Git via .gitignore.

⭐ Mantido por Victor


