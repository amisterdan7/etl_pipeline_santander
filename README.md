# 🏦 ETL Pipeline - Marketing Bancário

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Descrição

Pipeline ETL (Extract, Transform, Load) desenvolvido para otimizar estratégias de marketing bancário através de hiperpersonalização de comunicação. O projeto integra Python e Engenharia de Dados para automatizar o processamento de dados de clientes e gerar mensagens personalizadas utilizando Inteligência Artificial Generativa.

## 🎯 Objetivo

Automatizar o processo de comunicação bancária personalizada, extraindo dados de clientes, enriquecendo-os com mensagens de marketing geradas por IA Generativa (GPT-4) e integrando os resultados ao ecossistema bancário através de APIs REST.

## 🏗️ Arquitetura do Pipeline

### **Extract (Extração)**
- Leitura de dados de clientes a partir de arquivos CSV
- Validação e limpeza inicial dos dados
- Carregamento de informações estruturadas para processamento

### **Transform (Transformação)**
- Processamento e enriquecimento de dados utilizando Python
- Integração com IA Generativa (GPT-4) para criação de mensagens personalizadas
- Aplicação de regras de negócio e segmentação de clientes
- Geração de conteúdo contextualizado baseado no perfil de cada cliente

### **Load (Carga)**
- Envio dos dados processados via API REST
- Atualização do ecossistema bancário com informações enriquecidas
- Registro de logs e métricas de execução

## ✨ Funcionalidades

- ✅ Extração automatizada de dados de clientes (CSV)
- ✅ Processamento e transformação de dados com Python
- ✅ Geração de mensagens personalizadas usando IA Generativa
- ✅ Integração com APIs REST para carga de dados
- ✅ Validação e tratamento de erros
- ✅ Logging e monitoramento de execução

## 🛠️ Tecnologias Utilizadas

- **Python 3.8+**: Linguagem principal do projeto
- **Pandas**: Manipulação e análise de dados
- **OpenAI GPT-4**: IA Generativa para criação de mensagens personalizadas
- **Requests**: Comunicação com APIs REST
- **CSV**: Formato de entrada de dados
- **JSON**: Formato de intercâmbio de dados com APIs

## 📂 Estrutura do Projeto

```
etl-pipeline/
│
├── data/                   # Diretório para arquivos de dados
│   ├── input/             # Arquivos CSV de entrada
│   └── output/            # Dados processados
│
├── src/                   # Código fonte do pipeline
│   ├── extract/           # Módulos de extração
│   ├── transform/         # Módulos de transformação
│   └── load/              # Módulos de carga
│
├── config/                # Arquivos de configuração
│   └── settings.py        # Configurações do projeto
│
├── tests/                 # Testes unitários e de integração
│
├── logs/                  # Logs de execução
│
├── requirements.txt       # Dependências do projeto
├── .gitignore            # Arquivos ignorados pelo Git
└── README.md             # Documentação do projeto
```

## 🚀 Instalação

### Pré-requisitos

- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Chave de API da OpenAI (para funcionalidades de IA Generativa)

### Passos

1. Clone o repositório:
```bash
git clone https://github.com/amisterdan7/etl-pipeline.git
cd etl-pipeline
```

2. Crie um ambiente virtual:
```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

4. Configure as variáveis de ambiente:
```bash
cp .env.example .env
# Edite o arquivo .env com suas credenciais
```

## 💻 Uso

### Execução do Pipeline Completo

```bash
python main.py
```

### Execução por Etapa

**Extração:**
```bash
python src/extract/extract_data.py
```

**Transformação:**
```bash
python src/transform/transform_data.py
```

**Carga:**
```bash
python src/load/load_data.py
```

## 📊 Exemplo de Dados

### Entrada (CSV)
```csv
id,nome,idade,saldo,categoria
1,João Silva,35,15000,premium
2,Maria Santos,28,5000,standard
```

### Saída (Processada com IA)
```json
{
  "id": 1,
  "nome": "João Silva",
  "mensagem_personalizada": "Olá João! Como cliente Premium com saldo de R$ 15.000, temos uma oportunidade exclusiva de investimento para você...",
  "categoria": "premium"
}
```

## 🔐 Segurança

- Credenciais e chaves de API devem ser armazenadas em variáveis de ambiente
- Nunca commite arquivos `.env` no repositório
- Utilize HTTPS para todas as comunicações com APIs externas

## 🤝 Contribuindo

Contribuições são bem-vindas! Siga os passos abaixo:

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👥 Autores

- **Equipe de Engenharia de Dados** - Desenvolvimento e manutenção

## 📞 Contato

Para dúvidas ou sugestões, abra uma issue no repositório.

---

**Desenvolvido com ❤️ pela Equipe de Engenharia de Dados**
