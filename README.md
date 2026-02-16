# 🏗️ Desafio de Infraestrutura - BSN

Repositório estratégico contendo a orquestração da infraestrutura, observabilidade e esteira de CI/CD para o ecossistema **BookStack**.

---

### 📂 Estrutura do Projeto

| Diretório | Função | Tecnologias |
| :--- | :--- | :--- |
| **`app-bookstack`** | Aplicação e Banco de Dados | PHP, MariaDB |
| **`proxy`** | Gerenciamento de SSL e Domínios | Nginx Proxy Manager |
| **`monitoramento`** | Observabilidade | Prometheus, Exporters |
| **`cicd`** | Automação de Deploy | GitLab, GitLab Runner |

---

### ⚙️ Como Utilizar

1. **Configuração de Ambiente:**
   Copie o arquivo de exemplo e preencha suas credenciais:
   ```bash
   cp .env.example .env

   Rede Interna:
Crie a rede necessária para a comunicação dos containers:

Bash
docker network create proxy-nw
Deploy:
Acesse a pasta desejada e suba os serviços:

Bash
docker-compose up -d
