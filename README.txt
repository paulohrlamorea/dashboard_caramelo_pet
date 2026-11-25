README – Mini-projeto Power BI: Dashboard com KPIs

Contexto do Projeto

Você foi contratado pelo Augusto, gerente de vendas da empresa Caramelo Pet, que está com o seguinte problema:
Dados de vendas espalhados em vários arquivos Excel.

Arquivos separados por:
•	País, 
•	Cidade,
•	Produtos,
•	Categorias e subcategorias,
•	Vendedores;
•	Venda;

Objetivo
Construir um relatório em Power BI que:
•	Integre todas essas fontes;
•	Tenha modelo de dados limpo;
•	Traga KPIs de vendas, lucro e participação de mercado;
•	Traga análises de tempo;
•	Gere insights e recomendações estratégicas .

1. Preparação e Carregamento dos Dados
1.1 Verificar requisitos antes de começar
•	Ter Power BI Desktop atualizado;
•	Ter todos os arquivos de vendas e dimensões salvos localmente;
•	Conferir estrutura de pastas: Pasta de Dimensões (ex.: Dimensões)
•	Pasta de Vendas (ex.: Vendas) 

1.2 Criar tabelas dimensões e fatos no Power Query
Garantir que:
•	Cada tabela de dimensão tenha uma chave primária única (ProdutoID, CidadeID etc.);
•	Tipos de dados corretos (texto, número, data);
•	Colunas estejam padronizadas (nomes e tipos);
•	Adicionar colunas auxiliares se achar necessário (ano, mês etc.) 

2. Medidas e Indicadores Úteis

Vendas, Custo, Lucro e Market Share (use se achar necessário)
Medidas básicas:
• Receita Total = SUM(fact_Vendas[ValorVenda] ou [receita])
• CustoTotal =SUM(fact_Vendas[Custo])
• LucroBruto=[Receita Total]– [Custo Total]
• MargemBruta%=DIVIDE([LucroBruto], [Receita Total], 0)
• VendasporVendedor =SUM(fact_Vendas[ValorVenda])agrupado por Sales Rep.
• Rankingdevendedores (TOP N) por receita.
• Tabelacomvendas, margememarketshare por vendedor, se fizer sentido.
• YTD(Year-to-Date)– Receita_YTD
• Receita_YTD =TOTALYTD([Receita Total], dim_Calendario[Data])
• YTDLY(Year-to-Date do ano anterior)
• Receita_YTD_LY = CALCULATE([Receita_YTD], SAMEPERIODLASTYEAR(dim_Calendario[Data]))
• MTD(Month-to-Date)– Receita_MTD
• Receita_MTD =TOTALMTD([Receita Total], dim_Calendario[Data])
• MAT(Last12Months /Rolling 12)– Receita_MAT
• Receita_MAT =CALCULATE( [Receita Total], DATESINPERIOD(dim_Calendario[Data], MAX(dim_Calendario[Data]),-12, MONTH) )

3. Sugestão de Insights a Extrair

Identificar:
•	Países com maior/menor market share;
•	Cidades com lucro baixo ou margem apertada;
•	Vendedores com performance acima/abaixo da média;
•	Meses com picos e vales de receita (sazonalidade).

Recomendações estratégicas:
•	Regiões onde vale reforçar equipe ou marketing;
•	Produtos ou categorias com maior potencial de crescimento;
•	Ajustes na carteira de clientes/vendedores;
•	Registrar as recomendações em uma página dedicada ou em um resumo textual 

4. Entrega e Apresentação

Entregar um relatório dashboard em arquivo .pbix, com pelo menos:
•	2 tabelas;
•	3 métricas calculadas;
•	2 indicadores;
•	4 gráficos (de tipos diferentes)
•	1 resumo textual dos insights obtidos respondendo para Augusto sobre o negócio 
Obs.: Use quantas páginas achar necessário.


Contato do Professor
Rodrigo Garcia Brunini 
Cientista de Dados | Desenvolvedor de Projetos Professor | Tutor na EBAC 
LinkedIn: https://www.linkedin.com/in/rgbrunini
