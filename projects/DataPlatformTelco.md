# Data Platform Telco

Tal projeto tinha como objetivo a modernização de uma plataforma de dados cujo objetivo era coletar, transformar e armazenar dados relacionados aos CRDs gerados a partir do tráfego das redes de antenas. Esses dados incluíam informações sobre ligações, mensagens, tráfego de internet e geolocalização de aparelhos telefônicos.

## Arquitetura

![arquitetura](/img/DataPlatformArch.png)

### Componentes

- A solução era composta por uma VM on-premises que recebia arquivos .DAT e os armazenava em seu disco local.

- Por meio de uma conexão privada entre o ambiente on-premises e o Google Cloud Platform (GCP) (Interconnection), os arquivos eram transferidos para um NFS no GCP via script Shell.

- Esse NFS estava anexado a um Managed Instance Group, que realizava o upload dos arquivos para o Cloud Storage por meio de outro script Shell.

- Além disso, foi implementada uma DAG no Apache Airflow para processar os dados utilizando o Cloud Data Fusion e armazenar os resultados do ETL no BigQuery.