# Data Platform Seguradora

Este projeto teve como objetivo a implementação de uma plataforma de dados do zero para a companhia. Antes desta iniciativa, houve uma tentativa frustrada de implementação de um Data Lake, devido à falta de maturidade técnica do cliente para conduzir essa implantação.


## Arquitetura

![arquitetura](/img/DataPlatformSeguradora.png)

### Componentes

### Orquestração de Data Pipelines
- Implementação da camada de orquestração dos data pipelines utilizando **Airflow (Cloud Composer)**.

### DAG: Transient to Trusted
- **Camada "Data Collector"** implementada com jobs Spark executados no **Dataproc Serverless**. Inicialmente, todos os dados são armazenados na camada **transient**.
- **Spark Job** para geração da camada **raw** a partir da camada **transient**. Após a geração bem-sucedida dos arquivos na camada **raw** (formato Parquet), os arquivos na camada **transient** são removidos.
- **Spark Job** para geração da camada **trusted** a partir da camada **raw**. Os dados são armazenados no **BigQuery**, previamente tratados pelo Spark Job.

### DAG: Trusted to Datamart
- **Jobs BigQuery** para geração da camada **refined** a partir da camada **trusted**.
- **Jobs BigQuery** para geração da camada **datamart** a partir da camada **refined**.
- A camada **Datamart** é disponibilizada tanto no **BigQuery** quanto no **Cloud Storage**.

### Analytics
- **Power BI** conectado como camada de análise e visualização dos dados.


[Voltar](/README.md)