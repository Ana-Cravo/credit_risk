# 🏦 Projeto Final – Predição de Risco de Crédito com Machine Learning

## 📖 Descrição

Este projeto foi desenvolvido como trabalho final do Módulo 01 do curso de Machine Learning e Visão Computacional da SCTEC.

O objetivo consiste em desenvolver um modelo de Machine Learning capaz de prever a inadimplência de clientes que solicitam empréstimos.

A previsão da inadimplência permite que instituições financeiras reduzam riscos, apoiem a tomada de decisão na concessão de crédito e aumentem a segurança das operações.

---

# 🎯 Problema de Negócio

Uma instituição financeira deseja identificar clientes com maior probabilidade de inadimplência antes da aprovação de um empréstimo.

A partir das características dos clientes, como idade, renda, tempo de emprego, finalidade do empréstimo e histórico de crédito, foi desenvolvido um modelo capaz de classificar se um cliente possui maior risco de não pagamento.

O objetivo é auxiliar analistas de crédito na tomada de decisão, reduzindo perdas financeiras e melhorando a qualidade da carteira de crédito. 

Instituições financeiras precisam avaliar o risco de crédito antes de conceder um empréstimo. Uma classificação incorreta pode gerar impactos financeiros e operacionais para o banco.

O modelo de Machine Learning desenvolvido tem como objetivo auxiliar na identificação de clientes com maior probabilidade de inadimplência, reduzindo riscos na concessão de crédito.

Entretanto, os erros de classificação possuem custos diferentes:

* **Falso Positivo (FP):** quando o modelo classifica um bom pagador como "risco de calote". Nesse caso, o banco pode negar crédito a um cliente que provavelmente honraria seus pagamentos, causando perda de uma oportunidade de negócio e possível redução de receita.

* **Falso Negativo (FN):** quando o modelo classifica um mau pagador como "seguro". Esse é um cenário mais crítico, pois o banco pode conceder crédito a um cliente com alto risco de inadimplência, aumentando as chances de prejuízo financeiro devido ao não pagamento do empréstimo.

Por esse motivo, além da acurácia, é fundamental avaliar métricas como **Recall**, **Precisão (Precision)** e a **Matriz de Confusão**, buscando equilibrar a identificação dos clientes de risco sem prejudicar bons clientes.


---

# 📊 Dicionário de Dados
|Original  | Coluna | Descrição |
|----------|--------|-----------|
| person_age | idade_pessoa | Idade do cliente |
| person_income | renda_pessoa | Renda anual do cliente |
| person_home_ownership | tipo_residencia | Situação da residência (alugada, própria, etc.) |
| person_emp_length | tempo_emprego | Tempo de emprego em anos |
| loan_intent | finalidade_emprestimo | Finalidade do empréstimo |
| loan_grade | classificacao_emprestimo | Classificação de risco do empréstimo |
| loan_amnt | valor_emprestimo | Valor solicitado |
| loan_int_rate | taxa_juros_emprestimo | Taxa de juros aplicada |
| loan_status | status_emprestimo | Variável alvo (0 = adimplente / 1 = inadimplente) |
| loan_percent_income | percentual_renda_comprometida | Porcentagem da renda comprometida |
| cb_person_default_on_file | historico_inadimplencia | Y/N |
| cb_person_cred_hist_length | tempo_historico_credito | Tempo histórico de crédito |
| coluna criada | comprometimento_renda | (loan_amnt / person_income) * 100 |

---

# 🛠 Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- Scikit-Learn
- Imbalanced-Learn
- Jupyter Notebook
- Git
- GitHub

---

# 📁 Estrutura do Projeto

```text
credit_risk/
│
├── README.md
├── requirements.txt
├── projeto_credit_risk.ipynb
├── .gitignore
└── credit_risk_dataset.csv (download manual)
```

---
## Pré-requisitos

Antes de executar este projeto, verifique se o **Python 3.12.0** está instalado em seu computador.

### 1. Verificando a versão do Python

Abra o terminal do seu sistema operacional e execute um dos comandos abaixo:

```bash
python --version
```

Caso não funcione, tente:

```bash
python3 --version
```

Se o Python estiver instalado corretamente, será exibida uma mensagem semelhante a:

```text
Python 3.12.0
```

Se o Python não estiver instalado ou a versão for diferente da recomendada, faça o download da versão **Python 3.12.0** no site oficial:

https://www.python.org/downloads/release/python-3120/

> **Importante (Windows):** durante a instalação, marque a opção **"Add Python to PATH"** antes de clicar em **Install Now**.

---

## Clonando o repositório

Clone este repositório utilizando o Git:

```bash
git clone https://github.com/Ana-Cravo/credit_risk.git
```

Entre na pasta do projeto:

```bash
cd credit_risk
```
## Obtendo o conjunto de dados

Por questões de tamanho e para manter o repositório mais leve, o arquivo da base de dados (`.csv`) não está versionado no GitHub.
> **Observação:** o arquivo `.csv` foi incluído no `.gitignore`, portanto não faz parte do repositório Git. Após realizar o download da base de dados, copie o arquivo para a pasta raiz do projeto antes de executar o notebook.

Faça o download do dataset no link abaixo:

**Base de dados (.csv):**
https://drive.google.com/file/d/1R4WCMc_56lv3fMaDalUBAz5jSxeZOcwI/view?usp=sharing

Após o download, copie o arquivo `.csv` para a pasta raiz do projeto, conforme a estrutura abaixo:

```text
credit_risk/
│
├── projeto_credit_risk.ipynb
├── README.md
├── requirements.txt
├── credit_risk_dataset.csv (download manual)
└── .venv/
```

## Criando o ambiente virtual

Recomenda-se utilizar um ambiente virtual para isolar as dependências do projeto.

### Windows (Prompt de Comando)

```cmd
python -m venv .venv
```

Ativação:

```cmd
.venv\Scripts\activate
```

### Windows (PowerShell)

```powershell
python -m venv .venv
```

Ativação:

```powershell
.\.venv\Scripts\Activate.ps1
```

### Linux

```bash
python3 -m venv .venv
```

Ativação:

```bash
source .venv/bin/activate
```

### macOS

```bash
python3 -m venv .venv
```

Ativação:

```bash
source .venv/bin/activate
```

Após a ativação, o terminal deverá exibir o nome do ambiente virtual, por exemplo:

```text
(.venv)
```

---

## Instalando as dependências

Com o ambiente virtual ativado, instale todas as bibliotecas necessárias:

```bash
pip install -r requirements.txt
```

---

## Executando o projeto

Inicie o Jupyter Notebook:

```bash
jupyter notebook
```

ou, se preferir utilizar o Visual Studio Code, abra a pasta do projeto e selecione o interpretador correspondente ao ambiente virtual **.venv** antes de executar o notebook.


---


# 📈 Resumo Executivo

Durante a Análise Exploratória dos Dados (EDA) foram identificados valores ausentes, registros duplicados e outliers, que foram tratados durante a etapa de preparação dos dados.

As variáveis numéricas apresentaram distribuições assimétricas, justificando a utilização da mediana na imputação dos valores ausentes e a manutenção de alguns outliers representativos do cenário real de crédito.

Também foi identificado desbalanceamento entre clientes adimplentes e inadimplentes, corrigido posteriormente com técnicas de balanceamento.

Foram treinados e comparados dois modelos de Machine Learning:

- Decision Tree Classifier
- K-Nearest Neighbors (KNN)

O desempenho foi avaliado utilizando Accuracy, Precision, Recall, F1-Score e Matriz de Confusão, além do monitoramento de overfitting.

## 🏆 Veredito Final

Após a comparação dos modelos, a **Árvore de Decisão (Decision Tree)** apresentou o melhor equilíbrio entre desempenho, capacidade de generalização e interpretação dos resultados.

Por esse motivo, foi recomendada como o modelo mais adequado para implantação em um sistema de apoio à decisão na concessão de crédito.

---

# 👩‍💻 Autora

**Ana Cravo**

Projeto desenvolvido para conclusão do curso de Machine Learning e Visão Computacional – SCTEC.