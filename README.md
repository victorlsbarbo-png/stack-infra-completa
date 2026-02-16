Desafio de Infraestrutura - BSN (BookStack Network)
Este repositório centraliza a orquestração de uma infraestrutura completa, escalável e monitorada para o BookStack. O projeto utiliza Docker para garantir portabilidade e automação de ponta a ponta, desde o roteamento de tráfego até a esteira de CI/CD.

📋 Arquitetura da Solução
A infraestrutura está dividida em camadas lógicas para facilitar a manutenção e garantir alta disponibilidade dos dados:

Application Layer (app-bookstack): Core do sistema utilizando PHP (Laravel) e persistência de dados em MariaDB.

Traffic Management (proxy): Gerenciamento de terminações SSL/TLS e domínios via Nginx Proxy Manager (NPM).

Observability Stack (monitoramento): Coleta de métricas e performance via Prometheus e exportadores específicos.

CI/CD Pipeline (cicd): Automação de builds, testes e deploy contínuo através do GitLab e GitLab Runner.

📂 Estrutura de Diretórios
Plaintext
.
├── 📂 app-bookstack   # Container da aplicação BookStack & Database MariaDB
├── 📂 monitoramento   # Stack de métricas (Prometheus, Grafana, Exporters)
├── 📂 proxy           # Nginx Proxy Manager para roteamento e Let's Encrypt
└── 📂 cicd            # Automação de esteira com GitLab Self-Hosted
⚙️ Pré-requisitos & Instalação
1. Preparação do Ambiente
Certifique-se de ter o Docker e o Docker Compose instalados (v2.0+ recomendado).

2. Configuração de Variáveis
Não versione credenciais. Para configurar o ambiente:

Bash
cp .env.example .env
nano .env # Preencha com suas senhas e domínios
3. Deploy da Infraestrutura
Para subir o ambiente completo, você pode executar o deploy por módulos:

Bash
# Rede do Proxy (Essencial para comunicação entre containers)
docker network create proxy-nw

# Subir os serviços
docker-compose -f proxy/docker-compose.yml up -d
docker-compose -f app-bookstack/docker-compose.yml up -d
🛡️ Gestão de Backup & Segurança
Backups: Recomenda-se o dump periódico do banco de dados MariaDB.

SSL: Automatizado via Nginx Proxy Manager com certificados Let's Encrypt.

Network: Os containers rodam em redes isoladas, expondo apenas as portas necessárias ao Host.

🔗 Documentação de Apoio
Para entender melhor as ferramentas utilizadas neste projeto, consulte a documentação oficial:

📘 Documentação Oficial do BookStack

🐳 LinuxServer.io (Images Maintainer)

🦊 GitLab Self-Managed Documentation

📊 Prometheus & Monitoring Guide

⭐ Mantido por Victor
Foco em automação, infraestrutura como código e resiliência de dados.
