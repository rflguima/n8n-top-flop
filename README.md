# 🚀 Automação N8N: Monitor de Mercado "Top & Flop 5"

Monitoramento automatizado do mercado de ações utilizando n8n, Docker e a API Alpha Vantage. Este projeto demonstra proficiência em integração de APIs, manipulação complexa de dados (JSON/Array), lógica condicional e entrega de relatórios formatados (HTML) por e-mail.

---

## ✨ Funcionalidades e Tecnologias

Este projeto resolve o problema de ter que verificar manualmente as maiores altas e baixas do mercado, entregando um resumo diário e pronto para a tomada de decisão.

| Recurso | Tecnologia/Habilidade Demonstrada |
| :--- | :--- |
| **Orquestração** | **n8n** (Criação de workflows, uso de nós avançados). |
| **Gerenciamento** | **Docker** (`docker-compose` para portabilidade e execução padronizada). |
| **Coleta de Dados** | **API Alpha Vantage** (`TOP_GAINERS_LOSERS` endpoint). |
| **Processamento** | **Nós `Code`** (para limpar dados brutos do JSON e formatar em HTML). |
| **Lógica** | Uso de **`slice()`** e lógica de filtro para extrair Top 5 e Flop 5 de grandes listas. |
| **Entrega** | **OAuth 2.0 (Gmail API)** para envio seguro de e-mails. |
| **Agendamento** | Execução automática de **Segunda a Sexta-feira** via nó **`Cron`**. |

---

## 📈 Diagrama do Workflow

Abaixo está o fluxo lógico de como a automação funciona. O workflow é disparado diariamente, busca o resumo do mercado e envia um relatório formatado em HTML.



---

## 💻 Instalação e Execução (Via Docker)

Este projeto utiliza o Docker para garantir que o ambiente do n8n funcione em qualquer máquina.

### Pré-requisitos

* [Docker Desktop](https://www.docker.com/products/docker-desktop) (Instalado e em execução).
* Uma Chave de API da Alpha Vantage.
* Credenciais de API do Google Cloud para o Gmail (OAuth 2.0).

### 1. Iniciar o n8n

Use o comando `docker run` para iniciar o n8n na porta `5678`.

```bash
docker run -it --rm --name n8n_trabalho -p 5678:5678 -v ~/.n8n_data:/home/node/.n8n n8nio/n8n
