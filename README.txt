# Dashboard de Análise Bibliométrica e Relevância de Periódicos 📊

Este repositório contém a solução completa para o teste técnico de Análise de Dados/BI. O objetivo do projeto é analisar uma base de dados bibliométrica (SCImago/Scopus), realizar o tratamento de dados (ETL) e criar um painel interativo para extração de insights.

## 🛠️ Ferramentas Utilizadas
* **Python (Pandas):** Extração, Tratamento e Carga (ETL) dos dados brutos.
* **Power BI & DAX:** Modelagem, cálculos de métricas avançadas e visualização de dados.

## ⚙️ Etapa 1: ETL e Preparação dos Dados (Python)
O script de tratamento (`/scripts/etl_process.py` ou `.ipynb`) foi responsável por:
* Unificação e limpeza das bases de dados originais.
* Tratamento de tipos de dados textuais para numéricos (ex: correção de pontuação em métricas de impacto).
* Padronização de colunas essenciais para a modelagem no Power BI.

## 📈 Etapa 2: Modelagem e Decisões Técnicas no Power BI
Para garantir a precisão dos KPIs e a melhor experiência do usuário, as seguintes decisões técnicas foram tomadas:

1. **Filtro de Período/Ano Não Aplicável:** Foi identificado que a base de dados reflete um *snapshot* (retrato) consolidado do ano de 2022 (baseado na coluna `total docs. (2022)`). Para manter a integridade analítica, o filtro de ano não foi incluído, sendo adicionada uma Nota Técnica no dashboard justificando a decisão.
2. **Cálculo da Elite Q1 (%):** Utilização de DAX (`CALCULATE` e `COUNTROWS`) para encontrar dinamicamente a proporção de revistas pertencentes ao Primeiro Quartil de impacto.
3. **Ranking Dinâmico:** Implementação da função `RANKX` combinada com `ALLSELECTED` para gerar um Top 5 absoluto de periódicos, imune a quebras de contexto por outras colunas.
4. **Interatividade Avançada:** Criação de filtros hierárquicos (Drill-down geográfico de Região > País) e Drill-down interno no gráfico de barras de distribuição QUALIS.

## 📂 Estrutura do Repositório
* `/scripts`: Contém o código fonte do ETL em Python.
* `/dashboard`: Contém prints de tela do painel finalizado e Link para o Dashboard interativo.
* `/data`: Amostra dos dados gerados após a limpeza.

## 🚀 Como Executar
Para visualizar o ETL, abra o script Python na pasta `/scripts`.
Para interagir com o dashboard, abra o arquivo link público (Necessário uma conta), que esta na pasta /dashboard

---
**Desenvolvido por:** Guilherme Pires Oliveira
