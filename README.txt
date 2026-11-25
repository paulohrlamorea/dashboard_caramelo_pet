
# 📊 Dashboard de Performance Comercial — Caramelo Pet

Projeto de Business Intelligence desenvolvido no **Power BI** com foco em modelagem dimensional, tratamento de dados via ETL e visualização executiva para tomada de decisão.

![Preview do Dashboard](./Dashboard_Caramelo_Pet.png)
*(Dica: suba um print do painel com esse nome na raiz do repositório para a imagem aparecer aqui)*

---

## 🎯 O Problema de Negócio
As bases de dados da operação estavam fragmentadas em planilhas isoladas (vendas, produtos, categorias, geografia e representantes comerciais) com chaves inconsistentes que impediam o cruzamento direto das informações. 

O objetivo do projeto foi consolidar essas fontes em um modelo único para responder rapidamente a três perguntas centrais:
1. Qual é o volume real de faturamento líquido e lucro bruto da operação?
2. Qual é a margem real de rentabilidade por país e cidade?
3. Quais linhas de produtos e subcategorias puxam o resultado financeiro?

---

## 🛠️ O que foi feito na prática (Arquitetura e Desenvolvimento)

### 1. ETL e Limpeza de Dados (Power Query / Linguagem M)
* **Padronização de Chaves:** Remoção de caracteres sujos e espaços extras em códigos de produtos (`ProdutoID`), chaves de categoria (`CategoriaKey`) e localização geográfica (`País;Cidade`).
* **Desnormalização Controlada:** Unificação das tabelas auxiliares de *Categorias* e *Subcategorias* diretamente na dimensão `Produto`, eliminando tabelas soltas e simplificando o modelo.
* **Dimensão Calendário Dinâmica:** Criação via script M da tabela `dim_Calendario` baseada nas datas mínima e máxima da base de vendas, com ordenação cronológica correta dos meses.

### 2. Modelagem Dimensional (Star Schema)
* Estruturação em **Esquema Estrela**, mantendo a tabela fato `Vendas` no centro e conectada por relacionamentos de cardinalidade `1:*` (um para muitos) às dimensões `Produto`, `Geografia`, `RepresentanteVendas` e `dim_Calendario`.
* Garantia de integridade nos filtros e melhor performance no processamento das consultas.

### 3. Inteligência de Negócio e Métricas (DAX)
Criação de medidas explícitas para análise financeira e comparativa:
* **Receita Total:** Cálculo de faturamento líquido considerando unidades vendidas, preço de varejo e descontos aplicados (`SUMX` + `RELATED`).
* **Custo Total & Lucro Bruto:** Apuração direta dos custos padrão e resultado operacional.
* **Margem Bruta %:** Indicador de rentabilidade real sobre a receita líquida (`DIVIDE`).
* **Market Share %:** Participação percentual de cada país sobre o faturamento global (`CALCULATE` + `ALL`).
* **Inteligência Temporal:** Acompanhamento acumulado no ano (`TOTALYTD`) e comparação com o mesmo período do ano anterior (`SAMEPERIODLASTYEAR`).

### 4. UI/UX e Storytelling com Dados
* Prototipação prévia do layout priorizando hierarquia visual, leitura rápida de KPIs no topo e identidade visual aplicada à marca (*Caramelo Pet*).
* Inclusão de bloco de **Insights Executivos** diretamente no painel para destacar concentração de mix de produtos, sazonalidade e alavancas de margem.

---

## 📁 Estrutura do Repositório

* `pratique_powerbi.pbix` — Arquivo completo do Power BI (ETL, Modelo Estrela, Medidas DAX e Relatório).
* `Dashboard_Caramelo_Pet.pdf` — Versão exportada em alta resolução para visualização rápida sem necessidade do Power BI Desktop.

---

## 🚀 Como visualizar o projeto
1. **Visualização rápida:** Abra o arquivo `Dashboard_Caramelo_Pet.pdf` diretamente aqui no GitHub.
2. **Exploração interativa:** Baixe o arquivo `pratique_powerbi.pbix` e abra no **Power BI Desktop** (gratuito) para navegar pelos filtros, inspecionar o código M no Power Query e testar as medidas DAX.
