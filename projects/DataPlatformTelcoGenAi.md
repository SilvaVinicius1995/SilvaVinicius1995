# Data Platform Speech Analytics with GenAI

A Cliente estava buscando uma maneira eficiente de transcrever e analisar chamadas de reclamação de clientes. O objetivo era converter gravações de chamadas em texto para análise subsequente usando IA. As informações desejadas incluem a classificação das reclamações, a sumarização das chamadas, a extração de entidades específicas e a análise da duração das chamadas. Essa solução precisava suportar um volume de 3 milhões de arquivos de áudio por mês, com picos elevados de processamento.


## Arquitetura

![arquitetura](/img/DataPlatformTelcoGenAI.png)

### Componentes

O desenvolvimento e a integração envolveram o uso da API Speech-to-Text do Google para transcrição de áudio e a geração de Variáveis Cognitivas com GEN AI, com base no fluxo de eventos das gravações de áudio da TIM, utilizando EventArc, Cloud Functions e Cloud Run. Todos os endpoints foram expostos e gerenciados pelo Apigee.

Pipelines de LLMOps foram implementados usando o Vertex AI para medir e monitorar o desempenho e a versionamento dos modelos.

## Os resultados

- Precisão da análise de sentimento de 76%.
- Precisão de 78% na identificação de motivadores em ambiente de produção.
- Melhoria de 19% na precisão da transcrição em ambiente de produção.
- Pipelines de LLMOps extraíram métricas dos prompts do LLM para garantir que mudanças nos prompts não impactassem os resultados retornados.

[Voltar](/README.md)