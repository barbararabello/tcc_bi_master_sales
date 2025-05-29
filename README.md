# Dashboard de Sales Intelligence - Trabalho final do curso de Pós Graduação

#### Aluno: Bárbara Rabello (https://github.com/barbararabello)
#### Orientador: Anderson Nascimento (https://github.com/insightds)
---
Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso.
---
### Resumo
Este trabalho teve como objetivo realizar a coleta, modelagem, tratamento e análise de dados de uma empresa fictícia do setor de alimentos, com foco na criação de um dashboard em PowerBI para geração de insights estratégicos.

Inicialmente, foi realizada a simulação de um banco de dados contendo informações sobre todos os processos relevantes para o negócio, como vendas, produtos, clientes e funcionários e o levantamento de requisitos essenciais para a entrega do projeto. A partir dessas informações, os dados foram estruturados utilizando o modelo multidimensional em esquema estrela, com o intuito de otimizar o desempenho em consultas analíticas.

Em seguida, os dados foram tratados e transformados para garantir a padronização, utilizando a ferramenta Pentaho na construção do processo de ETL.
Com os dados prontos, foi desenvolvido um dashboard interativo no Power BI, permitindo a análise de indicadores de desempenho (KPIs) de forma rápida, como resultados de vendas, sazonalidades, desempenho por categoria de produto, por região e perfil dos clientes.
Os resultados evidenciam o potencial das ferramentas de Business Intelligence na transformação de dados brutos em informações estratégicas para a tomada de decisões de negócio. 
### 1. Introdução
A crescente demanda por ferramentas que possibilitem a análise de grandes volumes de dados tem impulsionado o uso de soluções de Business Intelligence como apoio à tomada de decisões data-driven nas organizações. Nesse contexto, este trabalho apresenta o desenvolvimento de um projeto completo de Sales Intelligence, contemplando as etapas de coleta de dados, levantamento de requisitos, modelagem, tratamento e visualização de dados, com o objetivo de criar um dashboard interativo voltado à análise de desempenho de uma empresa fictícia do setor de alimentos. A proposta foi desenvolvida como requisito final do curso de pós-graduação BI Master da instituição de ensino PUC - RJ. 
A iniciativa envolveu a simulação de um banco de dados contendo informações comerciais essenciais de vendas, produtos, clientes e funcionários, estruturadas por meio da modelagem multidimensional em esquema estrela. O processo de ETL foi realizado utilizando a ferramenta Pentaho, que assegurou a padronização e consistência dos dados. O armazenamento em DataWarehouse dos dados já tratados ocorreu na ferramenta PostgreSQL e o resultado final consistiu na construção de um dashboard em Power BI, composto por diferentes visões de KPIs estratégicos, permitindo a análise de insights relevantes para o negócio. 

### 2. Modelagem
Após a análise exploratória dos dados e definição de requisitos, o primeiro passo do projeto consistiu na modelagem multidimensional do tipo estrela, muito utilizada em projetos de visualização e análise de dados. O modelo estruturou as informações disponíveis da seguinte forma:
1) Tabela Fato:
    -  sk_cliente: Código de identificação do cliente
    -  sk_produto: Código de identificação do produto
    -  k_funcionário: Código de identificação do funcionário
    -  sk_data: Código de identificação da data
    -  md_atd: Medida de quantidade
2) Tabelas de Dimensões: 
    -  Tempo: Contém informações referentes à data
    -  Produto: Contém dados relacionados ao estoque de produtos
    -  Cliente: Abrange informações da base de clientes
    -  Funcionário: Reúne dados da lista de funcionários
Imagem da modelagem final abaixo:
![image](https://github.com/user-attachments/assets/ff44bf08-4e2f-48bf-b3f7-80feaf20e185)

Com a modelagem finalizada e a tabela fato e dimensões implementadas no PostgreSQL, iniciou-se o processo de extração dos dados brutos, transformação, padronização dos campos e carregamento no data warehouse.
Para este processo, utilizou-se a ferramenta Pentaho, com as seguintes etapas:
-  Extração dos dados e carregamento em uma área de stage para transformação;
-  Seleção dos dados relevantes ao escopo do projeto;
-  Reclassificação de categorias de produtos;
-  Padronização de letras maiúsculas e minúsculas;
-  Padronização do campo de gênero dos clientes;
-  Junção das tabelas de produto e categoria, com o objetivo de unificar informações contidas em tabelas distintas;
-  Carregamento dos dados tratados nas tabelas de dimensão e fato;
-  Criação de job para automatização dos processos de ETL.
Como etapa final, o projeto consolidou-se por meio do desenvolvimento de um dashboard interativo no Power BI, voltado à visualização e análise dos dados.

### 3. Resultados
O resultado final de todo o processo de modelagem e tratamento dos dados consistiu na construção de um dashboard interativo no Power BI, destinado ao uso interno dos colaboradores da empresa. A solução desenvolvida tem como objetivo sustentar tomadas de decisões estratégicas e facilitar a análise de resultados, por meio de visualizações dinâmicas e orientadas por dados.
O dashboard é composto por três telas, cada uma com indicadores-chave de desempenho (KPIs) específicos, conforme descrito a seguir:

Tela 01 – Visão Geral:
-  Indicadores gerais de receita, número de pedidos e ticket médio;
-  Evolução das vendas e do número de pedidos ao longo do tempo;
-  Desempenho de vendas por funcionário;
-  Filtros por data e por funcionário.
  
![image](https://github.com/user-attachments/assets/b9dadef2-6c13-4fa0-a3eb-4478706e5678)

Tela 02 – Produtos:
-  Quantidade total de produtos vendidos;
-  Volume de vendas por produto;
-  Evolução da quantidade de produtos vendidos ao longo do tempo;
-  Vendas por localidade;
-  Vendas por categoria de produto;
-  Filtros por data, categoria e país.
  
![image](https://github.com/user-attachments/assets/22856903-c4c3-47e3-96b5-59b4f8cd1edf)

Tela 03 – Clientes:
-  Número total de clientes cadastrados na base;
-  Recorrência de compras, receita e ticket médio por cliente;
-  Distribuição da base de clientes por gênero;
-  Localização geográfica dos clientes;
-  Filtros por data, gênero e país.

![image](https://github.com/user-attachments/assets/a78733b0-46e9-4425-b284-73c9cd7a1419)

A partir da entrega do dashboard, tornou-se possível identificar tendências de compra, padrões de recorrência, preferências por categorias de produtos e variações sazonais nas vendas. Dessa forma, o projeto atendeu plenamente aos requisitos definidos na fase inicial.
O Documento de Requisitos encontra-se disponível no repositório sob o nome “Documento de Requisitos”, e o arquivo do dashboard está nomeado como “Dashboard_sales_intelligence”.

### 4. Conclusões

O produto final demonstrou-se eficaz no atendimento aos requisitos levantados inicialmente, proporcionando uma ferramenta sólida para análises orientadas a dados. O dashboard possibilitou a identificação de tendências de consumo, sazonalidades de vendas, desempenho por colaborador e perfil dos clientes, sendo um apoio importante à tomada de decisões gerenciais. 
Este trabalho reforça o valor estratégico da integração entre modelagem de dados, processos de ETL e visualização interativa como componentes essenciais para projetos de inteligência de negócios bem-sucedidos.

---

Matrícula: 231.101.021
Pontifícia Universidade Católica do Rio de Janeiro
Curso de Pós Graduação *Business Intelligence Master*
