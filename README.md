## Storytelling sobre o problema

Um homem decide comprar uma casinha de cachorro online com entrega rápida. Após algumas semanas, a casinha chega, mas ele percebe que o tamanho está errado. Tentando devolver o produto, ele enfrenta dificuldades no processo de devolução online, o que o deixa frustrado. Sem sucesso pela internet, ele vai até uma pet shop local, onde finalmente consegue resolver o problema e trocar a casinha por uma de tamanho adequado.

## O que esperamos aprender com esse projeto?

De forma geral, esta iniciativa nos trará:
- Uma visão mais aprofundada da arquitetura de um dos principais provedores de material e alimentos para animais.
- Maior entendimento sobre os padrões utilizados.
- Oportunidades no setor.

## Perguntas que precisamos responder:

- Como são geradas divergências na devolução?
- Quais são as restrições de regulamentação nacional e internacional?
- Quais são os requisitos contábeis e fiscais?
- O que meu cliente busca?

## Principais riscos:

Os principais riscos relacionados à devolução de produtos incluem:
- Prazo de devolução, que deve atender à Lei do Consumidor.
- Risco de fraude: é importante identificar se o produto já foi usado.
- Armazenamento adequado.
- Devoluções incorretas.
- Regulamentações do MAPA.
- Processos de destruição ou reuso de produtos devolvidos.

## Plano para aprender e reduzir riscos:

1. **Plano de Aprendizagem**:
   - Identificar e mapear todos os processos de devolução.
   - Realizar entrevistas com stakeholders para entender pontos críticos.
   - Validar as regulamentações nacionais e internacionais aplicáveis.

2. **Plano para Reduzir Riscos**:
   - Estabelecer processos de auditoria para devoluções.
   - Implementar sistemas de rastreamento para evitar fraudes.
   - Garantir que o armazenamento e a logística estejam em conformidade com regulamentações.

## Stakeholders e expectativas:

- **Clientes**: Esperam uma devolução rápida e eficiente.
- **Lojas físicas**: Querem uma integração perfeita com o estoque e os pedidos online.
- **Equipe de TI**: Espera que a arquitetura seja escalável e fácil de manter.

## Principais problemas que podem surgir:

- Insatisfação dos clientes devido a falhas nas devoluções.
- Inconsistência de estoque.
- Atrasos ou erros nos reembolsos.

## Componentes da arquitetura:

- **Autoatendimento (Totem de Loja)**: Processa devoluções diretamente nas lojas físicas.
- **ERP Frente de Loja**: Sincronizado com o ERP Central para atualizar o estoque.
- **ERP Central**: Gerencia estoque, pedidos, logística e processos financeiros.
- **Pedidos**: Sistema de vendas online que integra a devolução de produtos.
- **Plataforma de Eventos**: Coordena a comunicação entre os sistemas.
- **Gateway de Pagamentos**: Processa os reembolsos.
- **Motor de Processamento de Imagens**: Valida imagens dos produtos devolvidos.
- **API Gateway (Outbound)**: Gerencia comunicações com sistemas externos.

## Requisitos importantes:

- **Sincronização entre sistemas**: Garante que o estoque esteja atualizado em tempo real.
- **Segurança de dados**: Protege transações financeiras e informações sensíveis.
- **Eficiência no processamento de devoluções**: Fundamental para uma boa experiência do cliente.
- **Escalabilidade**: A arquitetura deve crescer junto com a empresa.
- **Integração com sistemas de terceiros**: Facilita o processamento de reembolsos.

## Diagrama ajuda a raciocinar sobre:

- **Integração de sistemas**: Mostra como os diferentes sistemas se integram.
- **Processo de devoluções**: Visualiza o fluxo desde o início até o reembolso.

## Padrões essenciais no diagrama:

- **Arquitetura Orientada a Serviços (SOA)**: Facilita a manutenção e escalabilidade.
- **Plataforma de Eventos**: Desencadeia ações entre os sistemas de forma assíncrona.
- **Sincronização de Estoque**: Garante consistência nos dados de estoque.

## Padrões ocultos:

- **Desacoplamento através de APIs**: Facilita a troca de sistemas de terceiros.
- **Processamento assíncrono**: Permite operações contínuas, mesmo com algumas operações em andamento.

## Qual é o Metamodelo?

O metamodelo utilizado é baseado em uma **Arquitetura Orientada a Serviços (SOA)**. Isso significa que os componentes do sistema são modelados como serviços independentes que se comunicam entre si, principalmente por meio de APIs e eventos. Esse metamodelo permite flexibilidade e escalabilidade na arquitetura, garantindo que o sistema seja modular e de fácil manutenção.

## Pode ser discernido no diagrama único?

Sim, o metamodelo pode ser discernido no diagrama único. A arquitetura é construída com base em componentes desacoplados que se comunicam via APIs e eventos. A presença de serviços como ERP Central, ERP Frente de Loja, Plataforma de Eventos e API Gateway reflete o uso de um metamodelo SOA, onde cada serviço tem sua função específica e pode ser escalado ou alterado independentemente dos outros.

## O diagrama está completo?

O diagrama fornece uma visão clara dos principais componentes e suas interações, mas ainda poderia ser complementado com mais detalhes sobre fluxos específicos de dados e interações entre os módulos. Por exemplo, a interação com sistemas externos e o detalhamento de como o **Motor de Processamento de Imagens** valida as devoluções poderia ser mais explícito. Portanto, enquanto está claro e funcional, alguns detalhes adicionais poderiam enriquecer o entendimento.

## Poderia ser simplificado e ainda assim ser eficaz?

Sim, o diagrama poderia ser simplificado para focar nos principais componentes e seus fluxos mais críticos, como os processos de devolução, sincronização de estoque e reembolso. A remoção de detalhes menos críticos ou secundários poderia tornar o diagrama mais direto e fácil de entender, sem perder sua eficácia.

## Houve alguma discussão importante que vocês tiveram como equipe?

Uma discussão importante na equipe envolveu a **sincronização de estoque** entre as lojas físicas e o ERP Central. A equipe se preocupou com os possíveis problemas de inconsistência entre o estoque disponível nas lojas e o estoque registrado no sistema centralizado, especialmente durante o processo de devoluções. Foi necessário chegar a um consenso sobre como garantir a consistência e a atualização em tempo real.

## Que decisões sua equipe teve dificuldade para tomar?

A equipe teve dificuldade em decidir sobre a **integração do Gateway de Pagamentos** para reembolsos. A integração com sistemas de terceiros gerou incertezas, principalmente em relação à segurança dos dados financeiros dos clientes e à eficiência no processamento de reembolsos.

## Que decisões foram tomadas sob incerteza?

A decisão de **utilizar a Plataforma de Eventos** para coordenar as devoluções e o processamento assíncrono foi tomada sob incerteza. Embora o uso de eventos traga benefícios de desempenho e flexibilidade, houve receio quanto ao risco de atrasos ou falhas na comunicação entre os sistemas, especialmente em situações de alta demanda.

## Houve algum ponto de decisão sem retorno que o forçou a desistir de uma determinada escolha?

Sim, o ponto de não retorno foi a decisão de usar o **Motor de Processamento de Imagens** para validar as devoluções online. A equipe considerou outras abordagens, como uma validação manual, mas devido ao volume de devoluções e à necessidade de automação, foi decidido que a validação automatizada seria o melhor caminho. Após essa decisão, não havia como voltar para o processo manual sem comprometer a eficiência da operação.


## Arquiteturas no padrão C4:

1. **Nível Contexto**: Visão geral de como o sistema interage com o ambiente externo.
![undefined](https://github.com/user-attachments/assets/9d524ff3-1ced-47ba-a35b-51f4fe7434eb)

2. **Nível Container**: Mostra os principais contêineres (sistemas e serviços) envolvidos.
![undefined](https://github.com/user-attachments/assets/56aa3af1-64e0-4647-8418-ac517dc84dad)

3. **Nível Componente**: Detalha os componentes internos de cada contêiner.
- **E-commerce**:
![undefined (1)](https://github.com/user-attachments/assets/a7f5a4ce-ce0b-42da-979b-68d1e54a8cf4)
- **Auto Atendimento**:
![undefined (2)](https://github.com/user-attachments/assets/66894129-e6d9-4e2c-9e8f-6aaeea6b22e0)
- **ERP Frente de Loja**:
![undefined (3)](https://github.com/user-attachments/assets/fd19b52e-3dc5-40d3-bc41-49fe32ca1230)



