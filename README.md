# DAG de ingestão de dados

Esse repositório contém o código para execução de uma DAG (Directed Acyclic Graph), orquestrada pelo Apache Airflow, responsável por realizar a ingestão de músicas de uma playlist do Spotify para um banco de dados PostgreSQL.


## 1. Landscape
Antes de executar esta aplicação, é necessário garantir que você tenha as seguintes tecnologias instaladss:

- Python (versão 3.11.0 ou superior)
- Docker (versão 24.0.6 ou superior)
- Docker-compose (versão 2.21.0-desktop.1 ou superior)
- PostgreSQL (versão 15 ou superior)
- Conta de desenvolvedor no Spotify para acesso à API - [documentação SpotifyAPI](https://developer.spotify.com/)


## 2. Pré-requisitos do projeto
- Docker Preparado com as tecnologias
- Todas tecnologias adjacentes com suas versões especificadas 
- Dados mocks necessários disponiveis 
- Emulação de Network baseada na realidade 
- Garantir que todo pré-requesito necessário esteja liberado no nosso chocolatey

## 3. Como fazer o setup
### **Variáveis**
### Airflow Connection (interface)

1. Crie um banco de dados no PostgreSQL

2. Na seção **Admin >> Connections**, crie uma conexão

```
Connection Id= local_postgres
Connection Type= Postgres
Host = (servidor do banco de dados)
Database = (nome do banco de dados) 
Login = (usuário do banco de dados)
Password = (senha do banco de dados)
Port = (porta do servidor)
```

### Airflow Variables (interface)
1. No arquivo `airflow_variables.json` insira os valores das variáveis de acordo com seu contexto

2. Na seção **Admin >> Connections**, faça a o upload do arquivo e a importação das variáveis de ambiente


## Passo a passo:

Siga os passos abaixo para executar a aplicação:

### Iniciar Apache Airflow com Docker

1. Clone este repositório

   ```
   git clone https://github.com/AnaJuliaMM/comite_2602.git
   ```

2. Crie um arquivo `.env` na raiz do projeto e insira a seguinte configuração:

   ```
   AIRFLOW_UID=5000
   ```

3. Inicie o Apache Airflow

   ```
   docker-compose up -d
   ```

4. Acesse a interface gráfica do Apache Airflow em `localhost:8080`

### Execução
 Mude o status da DAG para ativo e execute o pipeline!

### Esse Lab tem o objetivo de:
- Aprender sobre diferentes origens e destino de dados
- Realizar um Pipeline completo de ingestão 
- Aprender sobre processo Batch e schedulagem
- Instanciar ferramentas
- Versionamento de código na prática
- Documentação 

## Estrutrura do projeto

- `dags:` arquivo da DAG
- `wiki:` recursos de documentação do pipeline
- `airflow_variables.json`: variáveis de ambiente para serem importadas no Airflow
- `docker-compose.yaml:` configuração Docker para execução do Apache Airflow no Docker




## Resultado esperado

Visualize os dados inseridos no banco de dados ✨

![Captura de tela 2024-02-26 105852](https://github.com/AnaJuliaMM/comite_2602/assets/123522605/29ab1cc4-0843-4711-85f7-7edf9ff1d55c)

Acesse nossos recursos: 🔗

- [Engenharia de Dados](./wiki/engenharia_dados.md)
- [Exemplo de uso da DAG](./wiki/dag_ingestao.md)