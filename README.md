# Dashboard Analítico do Mercado de Ações

Este dashboard analisa o desempenho de ações no mercado, fornecendo insights sobre volume total ao longo do tempo, valores médios mensais, variação da média de fechamento mês a mês (MoM) e utilizando narrativa inteligente para resumir os principais achados.

## Fontes de Dados

*   Banco de dados ou arquivos (CSV) contendo dados históricos das ações, incluindo:
    *   Data da negociação
    *   Código da empresa (ticker)
    *   Preço de abertura
    *   Preço de fechamento
    *   Preço máximo
    *   Preço mínimo
    *   Volume negociado

## Visualizações

*   **Volume Total ao Longo do Tempo:**
    *   Gráfico de linhas mostrando a evolução do volume total negociado ao longo do tempo.
    *   Segmentação por empresa para visualização individual.
*   **Tabela de Valores Médios por Mês:**
    *   Tabela ou matriz com os valores médios de abertura, fechamento, máximo e mínimo para cada mês.
*   **Variação da Média de Fechamento MoM (Month-over-Month):**
    *   Gráfico de colunas mostrando a variação percentual da média de fechamento de um mês para o outro.
    *   Linhas de tendência para identificar padrões.
*   **Narrativa Inteligente:**
    *   Resumo textual automático dos principais insights, destacando tendências, picos de volume e variações MoM.

![Dashboard_Analitico_mercado_acoes](https://github.com/user-attachments/assets/ca6782f3-5c3a-490e-a37e-2fdee872ed8c)


## Processo de ETL (Extração, Transformação e Carga)

1.  **Extração:** Dados extraídos da(s) fonte(s) usando o Power Query no Power BI Desktop.
2.  **Transformação:**
    *   Limpeza dos dados.
    *   Criação de colunas calculadas:
        *   `Mês = MONTH(TabelaDeAções[Data da negociação])`
        *   `Ano = YEAR(TabelaDeAções[Data da negociação])`
    *   Modelagem dos dados (relações entre tabelas, se necessário).
    *   Criação de medidas DAX (exemplos):
        *   `Volume Total = SUM(TabelaDeAções[Volume negociado])`
        *   `Média de Fechamento = AVERAGE(TabelaDeAções[Preço de fechamento])`
        *   `Média de Fechamento Mês Anterior = CALCULATE([Média de Fechamento], PREVIOUSMONTH(TabelaDeAções[Data da negociação]))`
        *   `Variação MoM = DIVIDE([Média de Fechamento] - [Média de Fechamento Mês Anterior], [Média de Fechamento Mês Anterior])`
3.  **Carga:** Modelo de dados carregado no Power BI Service (opcional).

## Narrativa Inteligente 

A Narrativa Inteligente gerou os seguintes insights:

*   **Tendência de Aumento no Volume:** Os volumes aumentaram em tendência, resultando em um aumento de 29,35% entre quarta-feira, 23 de fevereiro de 2022, e quinta-feira, 23 de fevereiro de 2023.
*   **Início da Tendência de Queda:** O volume iniciou uma tendência de queda em segunda-feira, 23 de janeiro de 2023, caindo 22,73% (57.442.811) em 31 dias.
*   **Queda Mais Acentuada:** O volume caiu de 252.725.113 para 195.282.302 durante a queda mais acentuada entre segunda-feira, 23 de janeiro de 2023, e quinta-feira, 23 de fevereiro de 2023.
*   **Participação de Fevereiro na Variação MoM:** Fevereiro representa 12,42% da Média de Fechamento MoM.

## Arquivo .pbix

O arquivo `Dashboard analítico do Mercado de ações - Narrativa Inteligente.pbix` contém o projeto completo.

## Como visualizar

Para visualizar interativamente, é necessário o Power BI Desktop. Para visualização online, use o Power BI Service https://app.powerbi.com/groups/me/reports/5de70668-d399-419c-b579-645a6b3d0649?ctid=e5a2d57f-82e3-43da-af1c-1a2cc1b42330&pbi_source=linkShare.

## Contato

Auriane F Sousa - aurianef8@gmail.com
