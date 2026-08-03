# Dashboard de Salários — imersao-python-alura

Este repositório contém um pequeno projeto em Streamlit que exibe um dashboard interativo com dados salariais da área de dados (Data Science, Data Engineering, ML, etc.). O objetivo é demonstrar visualizações e filtros para explorar salários por cargo, senioridade, tipo de contrato, local de residência e mais.

## Tecnologias

- Python 3.8+
- Streamlit
- pandas
- Plotly Express

## Estrutura do repositório

- `app.py` — aplicação Streamlit que carrega os dados, aplica filtros na barra lateral e gera métricas e gráficos (barras, histograma, pizza e mapa coroplético).
- `dados_imersao_final` — arquivo CSV com os dados usados no dashboard (também existe um link remoto usado por `app.py`).

## Como executar

1. Clone o repositório:

   git clone https://github.com/jeffsilverio/imersao-python-alura.git
   cd imersao-python-alura

2. Crie e ative um ambiente virtual (opcional, mas recomendado):

   python -m venv .venv
   # Windows
   .\.venv\Scripts\activate
   # macOS / Linux
   source .venv/bin/activate

3. Instale as dependências (Streamlit, pandas e plotly):

   pip install streamlit pandas plotly

4. Rode a aplicação:

   streamlit run app.py

A aplicação abrirá no navegador (normalmente em http://localhost:8501) e você poderá interagir com os filtros na barra lateral.

## Dados

O dataset contém colunas como:

- `ano` — ano da coleta
- `senioridade` — nível (Júnior, Intermediário, Sênior, Executivo)
- `contrato` — tipo de contrato (Tempo Integral, Contrato, Tempo Parcial)
- `cargo` — função/cargo
- `salario` — valor no campo `moeda`
- `moeda` — moeda original
- `usd` — salário convertido para USD (campo usado nas visualizações)
- `residencia` — país/território (sigla)
- `remoto` — presencial/remoto/híbrido
- `empresa` — nome da empresa (quando disponível)
- `tamanho_empresa` — porte da empresa
- `residencia_iso3` — código ISO3 do país (usado no mapa)

Observação: o arquivo `app.py` atualmente carrega os dados de uma URL remota (https://raw.githubusercontent.com/vqrca/dashboard_salarios_dados/refs/heads/main/dados-imersao-final.csv). Se preferir usar o arquivo local `dados_imersao_final`, altere a chamada em `app.py` para:

```python
# Exemplo para usar o arquivo local
df = pd.read_csv("dados_imersao_final")
```

ou renomeie o arquivo local para `dados-imersao-final.csv` e aponte para ele.

## O que o dashboard mostra

- KPIs principais: salário médio, salário máximo, total de registros e cargo mais frequente.
- Gráficos interativos:
  - Top 10 cargos por média salarial (gráfico de barras horizontal)
  - Distribuição de salários (histograma)
  - Proporção por tipo de trabalho (presencial/remoto) — gráfico de pizza
  - Mapa coroplético com salário médio por país (filtrado para cargos específicos, por exemplo Data Scientist)
- Tabela com os dados filtrados.

Use os filtros na barra lateral para selecionar anos, senioridade, tipo de contrato e porte da empresa — todas as visualizações e a tabela serão atualizadas automaticamente.

## Contribuições

Contribuições são bem-vindas! Abra uma issue para sugerir melhorias, correções de dados ou funcionalidades. Para contribuições código, envie um pull request com uma descrição clara do que foi alterado.

## Licença

Sinta-se à vontade para usar e modificar este projeto. Adicione um arquivo LICENSE se desejar escolher uma licença específica.

---

Projeto criado para exercícios da Imersão Python (Alura) — exemplo de dashboard interativo com Streamlit.