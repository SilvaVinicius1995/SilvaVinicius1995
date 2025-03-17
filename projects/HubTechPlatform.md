# Hub Tech Platform

A plataforma HUB foi desenvolvida para oferecer soluções simples e eficientes no setor de telecomunicações, com foco na integração de Serviços de Valor Agregado (SVA) com a TIM.

Anteriormente, os provedores de SVA — chamados de parceiros — mantinham uma relação direta com o setor responsável por essa integração. No entanto, com o aumento expressivo do número de provedores interessados em integrar seus serviços à TIM, a plataforma da operadora responsável por gerenciar os SVAs tornou-se sobrecarregada.

Para otimizar esse processo e garantir a eficiência de um setor altamente estratégico e lucrativo, foi criada a plataforma HUB. Essa solução especializada permite atender, organizar e monitorar os serviços de SVA, garantindo qualidade para a TIM e um suporte mais estruturado e eficiente para os parceiros.

## Arquitetura

![arquitetura](/img/HubTechPlatform.png)

### Componentes

- A plataforma segue uma arquitetura monolítica, na qual os módulos de assinatura, tarifação e mensageria são isolados em máquinas virtuais independentes.

- Compute Engines com bancos de dados segmentados para cada módulo.

- Cloud Load Balancing estabelecido para gerenciar a comunicação entre os serviços.

- A conectividade entre a plataforma e o sistema do cliente é realizada por meio de um checkpoint e VPN.


[Voltar](README.md)