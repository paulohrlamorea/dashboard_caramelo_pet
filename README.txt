Dashboard de Performance Comercial (Caramelo Pet)

O problema
Eu tinha várias tabelas separadas (vendas, produtos, cidades e vendedores) que não conversavam direito entre si. O objetivo era consolidar tudo em um só lugar para responder rápido a três perguntas: quanto estamos faturando, qual é a margem real de lucro e quais produtos puxam o resultado.

O que fiz na prática

Limpeza dos dados (Power Query)
Arrumei códigos de produtos e localidades que estavam sujos com letras e espaços sobrando. Também juntei as categorias direto na tabela de produtos para eliminar tabelas soltas e criei uma tabela de datas automática para filtrar o painel por ano e mês.

Organização das tabelas (Star Schema)
Coloquei a tabela de Vendas no centro e conectei as outras tabelas ao redor dela. Isso evita erros na hora de cruzar filtros e deixa o painel muito mais rápido.

Cálculos (DAX)
Criei as fórmulas para calcular faturamento líquido, custo total, lucro bruto, margem percentual, participação de cada país nas vendas e comparativos com o ano anterior.

Visual (UI/UX)
Desenhei o layout antes para ficar limpo, fácil de bater o olho e já entregando um resumo escrito com os principais pontos de atenção do negócio.

Arquivos do projeto

pratique_powerbi.pbix: Arquivo completo do Power BI com o tratamento, modelagem, cálculos e painel interativo.

Dashboard_Caramelo_Pet.pdf: Versão em PDF para visualização rápida sem precisar abrir o programa.

Como abrir
Para ver o visual rápido, basta abrir o arquivo PDF aqui mesmo. Se quiser testar os filtros e ver os cálculos por dentro, baixe o arquivo .pbix e abra no Power BI Desktop.
