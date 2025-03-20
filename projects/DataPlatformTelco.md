# Data Platform Telco

Tal projeto tinha como objetivo a modernização de uma plataforma de dados cujo objetivo era coletar, transformar e armazenar dados relacionados aos CRDs gerados a partir do tráfego das redes de antenas. Esses dados incluíam informações sobre ligações, mensagens, tráfego de internet e geolocalização de aparelhos telefônicos.

Havia concorrência entre o banco de dados e o processamento, impactando a produção e a extração de arquivos para a migração. Além disso, enfrentamos dificuldades na descriptografia das informações centrais da solução antiga, que era gerenciada por outro parceiro. Outro desafio foi o fim do suporte do fabricante para a principal tecnologia utilizada nessa solução. Além disso, um dos componentes da solução (Feeder) funcionava como uma "caixa preta" para nós.

## Arquitetura

![arquitetura](/img/DataPlatformArch.png)

### Componentes

- A solução era composta por uma VM on-premises que recebia arquivos .DAT e os armazenava em seu disco local.

- Por meio de uma conexão privada entre o ambiente on-premises e o Google Cloud Platform (GCP) (Interconnection), os arquivos eram transferidos para um NFS no GCP via script Shell.

- Esse NFS estava anexado a um Managed Instance Group, que realizava o upload dos arquivos para o Cloud Storage por meio de outro script Shell.

- Além disso, foi implementada uma DAG no Apache Airflow para processar os dados utilizando o Cloud Data Fusion e armazenar os resultados do ETL no BigQuery.

- Também foi implementado um serviço de conversão de requisições REST/SOAP para o sistema legado.

## Os resultados

Redução do tempo de consulta de 48 horas para aproximadamente 30 minutos.
Criação de 8 pipelines de transformação de dados, totalizando 5.000 etapas.
Precificação da estrutura do sistema judiciário.
Ambiente em conformidade com as leis de proteção de dados, como a LGPD.


[Voltar](/README.md)