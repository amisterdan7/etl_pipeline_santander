# 🚀 Pipeline ETL com Python (Santander Dev Week)

Este projeto é um pipeline de Engenharia de Dados completo (**E**xtract, **T**ransform, **L**oad) criado para automatizar a personalização de mensagens de marketing bancário.

O código demonstra como extrair dados de clientes, transformá-los gerando novas informações (mensagens personalizadas) e carregá-los de volta em um sistema externo via API.

## ⚙️ Arquitetura do Projeto

O projeto segue o fluxo clássico de ETL:

1.  **Extract (Extração):** Leitura de uma planilha CSV (`SDW2023.csv`) para identificar os usuários-alvo e busca dos dados cadastrais completos via API.
2.  **Transform (Transformação):** Lógica de enriquecimento de dados. Originalmente projetado para usar IA Generativa (GPT-4), neste laboratório utilizamos uma lógica de simulação para gerar mensagens de investimento personalizadas baseadas no nome do cliente.
3.  **Load (Carregamento):** Envio dos dados atualizados (com as novas mensagens) de volta para a API bancária.

---

## 🛠️ Adaptações Técnicas (API Pública)

Como o projeto original da Santander Dev Week utilizava uma API que foi descontinuada (offline), este projeto implementou uma solução robusta utilizando o **JSONPlaceholder**.

### Por que JSONPlaceholder?
O [JSONPlaceholder](https://jsonplaceholder.typicode.com) é uma API REST pública utilizada para testes e prototipagem. Ela foi escolhida para este projeto porque:

* **Disponibilidade:** Garante que o código execute sem erros de conexão (uptime de 99%).
* **Estrutura Compatível:** Fornece o endpoint `/users/{id}` que retorna objetos JSON contendo campos essenciais como `id` e `name`, mimetizando a estrutura necessária para o pipeline funcionar.
* **Simulação de CRUD:** Aceita requisições do tipo `GET` (para extração) e `PUT` (para simular o carregamento), retornando códigos HTTP 200 (sucesso) para validar a lógica do script.

---

## 📋 Detalhamento das Etapas

### 1. Extração (Extract)
O script lê o arquivo `SDW2023.csv` para obter uma lista de IDs de usuários (ex: `[4, 5, 6]`). Em seguida, itera sobre essa lista fazendo chamadas `GET` para a API:

```python
# URL da API de Testes
sdw2023_api_url = '[https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)'

# Busca dados do usuário (ex: ID 4)
response = requests.get(f'{sdw2023_api_url}/users/{id}')
