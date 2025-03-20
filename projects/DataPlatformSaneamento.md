# Data Platform Saneamento

O cliente possuía diversas fontes de dados que não estavam integradas ao seu Data Lake, o que dificultava a extração de informações e impactava a velocidade e a confiabilidade das decisões baseadas em dados. O principal desafio era a impossibilidade de incorporar os dados do Salesforce ao Data Lake existente, pois tal arquitetura não tinha camada de orquestração e impossibilidade de escabilidade, comprometendo, assim, o aproveitamento de informações cruciais. 


## Arquitetura

![arquitetura](/img/DataPlatfomSaneamento.png)

### Componentes

- Para ingerir dados do Salesforce e do Five9, a solução aproveita as práticas existentes da Iguá de armazenar dados brutos no S3. Utiliza ferramentas como o AppFlow e o AWS Glue (para flexibilidade, mas exigindo codificação) para ingestão de dados.

- Para a integração com o Data Lake, a solução transforma e armazena os dados na camada Silver usando o AWS Glue e o formato Parquet, garantindo o armazenamento em buckets privados e criptografados no S3. 

- Para gerenciar o fluxo de dados e monitorar erros, são utilizados o AWS Airflow (MWAA), o CloudWatch e o SNS. 

- Por fim, a solução permite consultar tanto o Data Lake novo quanto o existente usando o AWS Athena, facilitando o consumo de dados pelas ferramentas de inteligência de negócios.

## Os resultados

- Integração e acesso aprimorados aos dados
- Maior confiabilidade na tomada de decisões baseada em dados
- Melhor compreensão da jornada do cliente
- Atendimento ao cliente aprimorado
- Aumento da eficiência e produtividade

[Voltar](/README.md)