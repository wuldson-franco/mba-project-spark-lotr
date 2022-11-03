<h1>MBA-Project-LOTR</h1>
<p align="center">
  <a href="" rel="noopener">
 <img width=500px height=100px src="https://docs.delta.io/latest/_static/delta-lake-logo.png" alt="Project logo"></a>
</p>

<h3 align="center">Delta lake is an open-source project that enables building a Lakehouse architecture on top of existing storage systems such as S3, ADLS, GCS, and HDFS.</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

## 📝 Table of Contents

- [About](#about)
- [Architeture](#architeture)
- [Usage](#usage)
- [Built Using](#built_using)
- [Authors](#authors)

## 🧐 About <a name = "about"></a>


# Pyspark Guide

## Fase 1: Configurações dos dados da base do Kaggle: https://raw.githubusercontent.com/tianyigu/Lord_of_the_ring_project/master/LOTR_code/script.csv
    

## Dados Relacionados a Trilogia da Franquia "O Senhor Dos Anéis", os dados em questão são trechos retirados das falas ditas por seus personagem nessa trilogia.
## *Nessa Análise estaremos realizando a tradução desses trechos para o português, verificando qual personagem possui maior e a menor quantidade de diálogo.*

## Fase 2: Processamentos, Refinamentos e Joins
## São realizadas etapas de processamento em que são removidas colunas desnecessárias e preparação de tabelas com join para MDW modelagem com dados normalizados em formatos de conjunto de dados.

## Teremos a responsabilidade de enriquecer os dados, neste processo é onde tratamos os dados e refinamos para a área de negócios ou quem irá consumir os dados. 


![img_lotr](https://criticalhits.com.br/wp-content/uploads/2022/08/O-Senhor-dos-Aneis.jpg)



# 🔧 Architeture ELT Delta lake <a name = "architeture"></a>

![elt_delta](https://miro.medium.com/max/976/1*CH-5LyQjrpt3H1_kpOA8Xw.png)

## No projeto iremos lê os dados de um sistema de arquivos chamado *landing-zone* usando dependências de deltalake, que são pacotes .jar e estarão escritos na configuração de sessão do spark, com o qual é possível usar o framework **Delta Lake**. Após a execução deste script, os dados serão escritos no diretório passado no código, já dentro da tabela de escrita, será escrito um diretório chamado *_delta_log*, que é responsável por armazenar arquivos incrementais nos metadados da tabela, será algo como 000000000000000000000.json, 000000000000000000001.json... 
## O arquivo Json na pasta _delta_log terá as informações como add/remove parquet files (for Atomicity), stats (for optimized performance & data skipping), partitionBy for partition pruning), readVersions(for time travel), commitInfo(for audit).

## ⛏️ Built Using <a name = "built_using"></a>

- [Pyspark](https://spark.apache.org/docs/latest/api/python/index.html) - 3.1.1
- [Deltalake](https://docs.delta.io/latest/quick-start.html) 
- [Python 3.10](https://www.python.org/downloads/release/python-3100/)

## ✍️ Authors <a name = "authors"></a>

- [@carlosbpy](https://github.com/carlosbpy) - Idea & Initial work
- [@wuldson](https://github.com/wuldson-franco) - Case, Study & Pratice