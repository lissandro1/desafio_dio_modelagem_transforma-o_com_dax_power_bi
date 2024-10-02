## Bootcamp DIO - NTT DATA - Engenharia de Dados com Python

## *Desafio de Projeto -  Modelagem e Transformação de dados com DAX com Power BI*


### Processo de construção

**Tabelas**
- D_Produtos: Tabela dimensão que contém informações dos produtos, como ID, média e valor máximo de vendas.
- F_Vendas: É a tabela fato, contendo os dados de vendas, descontos, lucro, unidades vendidas, etc.
- D_Detalhes: Tabela dimensão que armazena informações como custo (COGS), lucro, vendas e detalhes associados ao produto.
- D_Produtos_Detalhes: Tabela dimensão que possui os detalhes do produto como preço de fabricação, preço de venda e unidades vendidas.
- D_Descontos: Tabela dimensão que contém informações sobre descontos e faixas de descontos.
- D_Calendário: Tabela dimensão de calendário para facilitar a análise temporal.

Com a ferrramenta Power Query do Power BI, houve também um processo transformação de colunas (colunas condicionais) e limpeza os dados para garantir consistência e qualidade, isso incluiu a remoção de duplicatas e padronização de formatos.

**Relacionamento e Cardinalidade**

No diagrama, a tabela F_Vendas tem relações com várias tabelas de dimensão (D_Produtos, D_Detalhes, D_Descontos, D_Calendário, etc.). Isso permite criar um modelo Star Schema, onde F_Vendas é a tabela central (fato) e as outras são tabelas de dimensão. 
A cardinalidade entre as tabelas é de 1:* (um para muitos) ou *:* (muitos para muitos), onde todas as tabelas dimensão se relacionam com a tabela fato (F_Vendas) por colunas chaves (ID) ou colunas em comum.

### Função DAX
 
A tabela D_Calendário foi criada a partir de uma função DAX, na qual ela foi gerada através das datas (coluna Date) da tabela de origem financials_origem, dando origem a todas as colunas dessa tabela (Data, Ano, Mês número, Dia da semana, Dia da semana texto).
 
A tabela apresenta granularidade a nível de DIA, ou seja, vendas realizadas por dia, então isso significa que seu nível de detalhe é muito grande, logo sua granularidade é alta.
As principais funcionalidades da tabela D_Calendário, além fornecer uma maneira estruturada de trabalhar com informações de tempo em análises e relatórios, são: facilitar agrupamentos e análises temporais, evitar redundância, facilitar a criação de medidas calculadas, criar filtros e cálculos com base em períodos de tempo com maior facilidade e garantir que os relatórios e dashboards utilizem a mesma lógica e estrutura temporal.

![desafio_dio_modelagem_transformação_com_dax_power_bi](https://github.com/user-attachments/assets/0f1b259e-43f4-4d57-8cdc-588b804e3c44)


