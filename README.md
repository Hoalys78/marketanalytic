# Análise de Vendas, Margens e Perdas — Vegetais (Rede de Supermercados)

**Resumo**
Projeto de análise de dados para avaliar vendas, margem e impacto de perdas em itens hortifrúti (vegetais). Objetivo: fornecer insights acionáveis para pricing, redução de perdas e promoção de itens de maior margem.

**Tabelas usadas**
- `item_categoria` — dimensão de itens e categorias.
- `registros_de_vendas` — fato de vendas (kg vendidos, preço, desconto, data/hora).
- `preco_atacado_diario` — custo diário por kg (atacado).
- `media_de_perda` — taxa média de perda por item (%).

**Modelo de dados**
Star schema:
- Fato: `Fato_Vendas` (registros_de_vendas transformada)
- Dimensões: `Dim_Item`, `Dim_Calendar`
- Tabelas auxiliares: `Custo_Diario`, `Perdas`

**Transformações (Power Query)**
- Conversão de tipos (Date, Time), criação de `Gross Sales` = `Quantity Sold (kilo)` * `Unit Selling Price`
- Normalização de colunas (trim, case)
- `Loss Rate (%)` convertido para decimal
- `Dim_Calendar` gerada com calendário contínuo

**Medidas chave (DAX)**
- `Total Vendas`, `Total Kg`, `Custo Total`, `Kg Perdidos`, `Custo Perdas`, `Lucro Bruto`, `Lucro Real`, `Margem %`, `Vendas LY`

**Páginas do relatório**
1. Visão Geral Executiva — KPIs, evolução mensal, vendas por categoria
2. Análise de Itens — Top 20, scatter Qty × Margem, tabela detalhada
3. Preço e Custo — evolução preço venda vs atacado
4. Perdas — itens com maior perda e custo associado
5. Storytelling e recomendações

**Principais insights (exemplo de entrega)**
- Itens X, Y e Z concentram 45% do faturamento e respondem por 60% do lucro.
- Item A tem alta rotatividade, mas margem negativa após perdas.
- Sazonalidade: meses M1–M2 aumentam vendas em 30%, porém elevam perdas.

**Entregáveis**
- `report.pbix` (Power BI file)
- README.md
- `Resumo_Executivo.pdf` (1 página)
- Screenshots dos dashboards (para portfólio)
- Script DAX e Power Query (M) usados

**Como reproduzir**
1. Coloque os CSVs em `data/`
2. Abra `report.pbix` e atualize os dados
3. Verifique `Dim_Calendar` e ajuste intervalo se necessário

**Autor / Contato**
- Hoalys — Analista de Dados / Portfólio
