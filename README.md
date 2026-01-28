# 📊 Análise de Faturamento Mensal com SQL no Metabase

Este repositório contém uma análise de dados desenvolvida em **SQL**, utilizando o **Metabase** disponibilizado pela **Escola DNC**, com foco no **total faturado por mês**, permitindo **filtro de data fornecido pelo usuário**.

O objetivo do projeto é demonstrar habilidades em **consulta SQL**, **agregação de dados**, **análise temporal** e **visualização de indicadores financeiros**.

---

## 🧠 Contexto do Case

**Case:** Total Faturado por Mês com Filtro de Data  
**Ferramenta de BI:** Metabase  
**Linguagem:** SQL  
**Fonte de Dados:** Base interna da DNC  
**Ambiente:**  
🔗 https://dex.dnc.group/browse

---

## 🗂️ Estrutura de Dados

### Tabela analisada
- **Orders**

### Principais campos utilizados
- `Subtotal` → valor monetário do pedido  
- `Created_At` → data de criação do pedido  

---

## 🎯 Objetivo da Análise

- Calcular o **total faturado mensal**
- Agrupar os dados por **mês e ano**
- Permitir que o usuário filtre os dados por **intervalo de datas**
- Facilitar a análise da **evolução do faturamento ao longo do tempo**

---

## 🧾 Query SQL Utilizada

```sql
SELECT
    SUM(Subtotal) AS total,
    MONTH(Created_At) AS Mes,
    YEAR(Created_At) AS Ano
FROM Orders

[[ WHERE {{input_data}} ]]

GROUP BY Mes, Ano
ORDER BY Ano, Mes;
```

---

## 🔍 Explicação da Query

- **`SUM(Subtotal)`** → Soma o faturamento total.
- **`MONTH(Created_At)`** → Extrai o mês da data do pedido.
- **`YEAR(Created_At)`** → Extrai o ano da data do pedido.
- **`{{input_data}}`** → Filtro dinâmico de data fornecido pelo usuário no Metabase.
- **`GROUP BY Mes, Ano`** → Agrega os dados mensalmente.
- **`ORDER BY Ano, Mes`** → Organiza os resultados cronologicamente.

---

## 📈 Visualização dos Dados

A visualização foi construída no **Metabase** em formato de **gráfico de barras**, permitindo a comparação do faturamento mensal entre diferentes anos.
---

### 📊 Faturamento mensal por ano (sem filtro de data)

![Faturamento mensal por ano](images/total_faturado_por_mes.png)

### 📅 Faturamento mensal com filtro de data aplicado (a partir de 2018)

![Faturamento mensal com filtro de data](total_faturado_por_mes_com_filtro.png)
---

### 🔎 Insights

- Crescimento ou queda de faturamento ao longo dos meses  
- Comparação de desempenho entre anos  
- Identificação de sazonalidade  
- Análise de picos de vendas  

---

## 🛠️ Tecnologias Utilizadas

- **SQL**
- **Metabase**
- **Banco de dados relacional**

---

## 📚 Aprendizados

- Uso de funções de data (`MONTH`, `YEAR`)
- Agregações com `SUM` e `GROUP BY`
- Criação de filtros dinâmicos no Metabase
- Organização de consultas para análise temporal
- Documentação de projetos de dados para portfólio

---

## 👤 Autor

Projeto desenvolvido como parte da formação em **Análise de Dados** na **Escola DNC**.

---

## ⭐ Observações

Este projeto faz parte do meu portfólio e tem fins **educacionais**, demonstrando boas práticas em **análise de dados com SQL** e **ferramentas de BI**.

