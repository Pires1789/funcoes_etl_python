# **ETL e Análise Exploratória de Dados em Python**

Este repositório contém uma coleção de funções Python projetadas para otimizar e agilizar processos de ETL (Extração, Transformação e Carga) e análise exploratória de dados. Essas funções são especialmente úteis para analistas de dados que desejam automatizar tarefas repetitivas e focar na análise e visualização de dados.

## Índice

- [Funções](#funções)
  - [`load_csv(file_path, delimiter=',', header=True)`](#1-load_csvfile_path-delimiter-headertrue)
  - [`clean_column_names(df)`](#2-clean_column_namesdf)
  - [`drop_missing_values(df, threshold=0.5)`](#3-drop_missing_valuesdf-threshold05)
  - [`transform_date_column(df, column_name, format='%Y-%m-%d')`](#4-transform_date_columndf-column_name-formaty-m-d)
  - [`aggregate_data(df, group_by_columns, aggregation_dict)`](#5-aggregate_datadf-group_by_columns-aggregation_dict)
  - [`filter_outliers(df, column_name, method='IQR')`](#6-filter_outliersdf-column_name-methodiqr)
  - [`join_dataframes(df1, df2, on_columns, how='inner')`](#7-join_dataframesdf1-df2-on_columns-howinner)
  - [`normalize_column(df, column_name)`](#8-normalize_columndf-column_name)
  - [`extract_features(df, column_name, new_columns)`](#9-extract_featuresdf-column_name-new_columns)
  - [`save_to_csv(df, file_path, index=False)`](#10-save_to_csvdf-file_path-indexfalse)
- [Padrões de Formatação de Datas](#padrões-de-formatação-de-datas)

## **Funções**

### 1. `load_csv(file_path, delimiter=',', header=True)`
   - **Descrição:** Carrega um arquivo CSV em um DataFrame do pandas.
   - **Parâmetros:**
     - `file_path` (str): Caminho para o arquivo CSV.
     - `delimiter` (str): Delimitador usado no CSV (por padrão, vírgula).
     - `header` (bool): Indica se o CSV contém um cabeçalho.
   - **Uso:** Facilita a leitura de arquivos CSV, com opções para ajustar delimitadores e cabeçalhos.

### 2. `clean_column_names(df)`
   - **Descrição:** Limpa e padroniza os nomes das colunas de um DataFrame.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame com nomes de colunas a serem limpos.
   - **Uso:** Remove espaços, caracteres especiais e transforma os nomes das colunas para minúsculas, facilitando o acesso e a manipulação.

### 3. `drop_missing_values(df, threshold=0.5)`
   - **Descrição:** Remove linhas ou colunas com valores ausentes com base em um limite de percentual.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame do qual remover valores ausentes.
     - `threshold` (float): Percentual mínimo de dados não ausentes necessário para manter uma linha ou coluna.
   - **Uso:** Auxilia na limpeza de dados, removendo linhas ou colunas com muitos valores ausentes.

### 4. `transform_date_column(df, column_name, format='%Y-%m-%d')`
   - **Descrição:** Converte uma coluna de datas para o formato especificado.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame contendo a coluna de datas.
     - `column_name` (str): Nome da coluna com datas.
     - `format` (str): Formato para converter as datas.
   - **Uso:** Padroniza o formato de datas em um DataFrame.

### 5. `aggregate_data(df, group_by_columns, aggregation_dict)`
   - **Descrição:** Realiza agregação de dados com base em colunas específicas.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame a ser agregado.
     - `group_by_columns` (list): Lista de colunas para agrupar.
     - `aggregation_dict` (dict): Dicionário definindo as funções de agregação para cada coluna.
   - **Uso:** Facilita a agregação de dados para análise resumida.

### 6. `filter_outliers(df, column_name, method='IQR')`
   - **Descrição:** Remove outliers de uma coluna com base em métodos estatísticos.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame com os dados.
     - `column_name` (str): Nome da coluna a ser filtrada.
     - `method` (str): Método para identificar outliers (por exemplo, 'IQR', 'Z-score').
   - **Uso:** Melhora a qualidade dos dados removendo outliers para análises mais precisas.

### 7. `join_dataframes(df1, df2, on_columns, how='inner')`
   - **Descrição:** Realiza a junção de dois DataFrames com base em colunas comuns.
   - **Parâmetros:**
     - `df1` (DataFrame): Primeiro DataFrame.
     - `df2` (DataFrame): Segundo DataFrame.
     - `on_columns` (list): Lista de colunas para a junção.
     - `how` (str): Tipo de junção (por exemplo, 'inner', 'left', 'right', 'outer').
   - **Uso:** Combina dois conjuntos de dados com base em colunas comuns.

### 8. `normalize_column(df, column_name)`
   - **Descrição:** Normaliza os valores de uma coluna para uma faixa padrão (0 a 1).
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame com a coluna a ser normalizada.
     - `column_name` (str): Nome da coluna a ser normalizada.
   - **Uso:** Facilita a análise comparativa ao normalizar os dados.

### 9. `extract_features(df, column_name, new_columns)`
   - **Descrição:** Extrai características adicionais de uma coluna e as adiciona como novas colunas.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame contendo a coluna de origem.
     - `column_name` (str): Nome da coluna a partir da qual extrair características.
     - `new_columns` (list): Lista de novos nomes de colunas para as características extraídas.
   - **Uso:** Adiciona novas variáveis úteis para análise a partir de colunas existentes.

### 10. `save_to_csv(df, file_path, index=False)`
   - **Descrição:** Salva um DataFrame em um arquivo CSV.
   - **Parâmetros:**
     - `df` (DataFrame): DataFrame a ser salvo.
     - `file_path` (str): Caminho para o arquivo CSV de destino.
     - `index` (bool): Indica se o índice do DataFrame deve ser incluído no CSV.
    - **Uso:** Cria um arquivo csv para exportar os dados neste formato.
   - **Uso:** Exporta os resultados de análises para um formato de arquivo amplamente utilizado.

## **Padrão de data**

Aqui podem ser encontrados os padrões de data mais comuns.

### Padrões de Formatação de Datas

| Símbolo | Descrição            | Exemplo       |
|---------|----------------------|---------------|
| `%Y`    | Ano com século       | 2023          |
| `%y`    | Ano sem século       | 23            |
| `%m`    | Mês (01-12)          | 07            |
| `%B`    | Nome completo do mês | July          |
| `%b`    | Abreviação do mês    | Jul           |
| `%d`    | Dia do mês (01-31)   | 26            |
| `%H`    | Hora (00-23)         | 14            |
| `%I`    | Hora (01-12)         | 02            |
| `%p`    | AM ou PM             | PM            |
| `%M`    | Minuto (00-59)       | 30            |
| `%S`    | Segundo (00-59)      | 45            |
| `%f`    | Microsegundos        | 123456        |
| `%z`    | Desvio UTC           | +0200         |
| `%Z`    | Nome do fuso horário | UTC           |
| `%j`    | Dia do ano (001-366) | 207           |
| `%U`    | Semana do ano (00-53) com domingo como primeiro dia da semana | 30            |
| `%W`    | Semana do ano (00-53) com segunda-feira como primeiro dia da semana | 30            |
| `%c`    | Data e hora          | Tue Jul 26 14:30:45 2023 |
| `%x`    | Data                 | 07/26/23      |
| `%X`    | Hora                 | 14:30:45      |

