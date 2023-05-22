# Ingestão de Dados no Databricks 
## Ingestão de dados do Olist utilizando Python e SQL para as camadas Raw, Bronze, Silver e Gold.

Nesse notebook utilizamos Python e SQl para realizar a ingestão dos dados da base do Olist nas camadas Raw, Bronze, Silver e Gold.

A camada Raw contém os arquivos CSV puro, sem tratamento, a cada ingestão os dados são sobrescritos.

A camada Bronze possui os dados em formato delta e adicionamos uma coluna do tipo Timestamp informando a data da carga de dados. A ingestão de dados dessa camada é incremental.

A camada Silver os dados são armazenados em formato delta, as devidas conversões foram feitas para armazenar os dados no formato desejado e os dado inseridos na camada Silver sempre são os dados mais recentes da camada Bronze que rankeamos usando o DENSE_RANK()

A camada Gold contém uma única grande tabela que consolida os dados da camada Silver, é através dessa tabela que os relatórios e visualizações serão gerados.

Criamos também alguns gráficos como exemplo de visualização de dados.
