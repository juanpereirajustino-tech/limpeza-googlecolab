# Limpeza e Filtragem de Dados RAIS 2025

## Sobre o projeto

Este projeto tem como objetivo realizar a exploração, análise e limpeza de uma base de dados da Relação Anual de Informações Sociais (RAIS), utilizando Python no Google Colab.

O tratamento foi realizado com o auxílio das bibliotecas Pandas e NumPy, buscando identificar valores ausentes, registros duplicados e possíveis inconsistências nos dados.

## Base de dados

A base utilizada contém informações referentes aos estabelecimentos e vínculos empregatícios, incluindo variáveis relacionadas a:

- Atividade econômica (CNAE);
- Município e UF;
- Quantidade de vínculos empregatícios;
- Natureza jurídica;
- Tamanho do estabelecimento;
- Tipo de estabelecimento;
- Indicador de RAIS negativa;
- CEP do estabelecimento;
- Informações de localização.

### Dimensões da base original

- **Registros:** 47.339
- **Variáveis:** 24
- **Valores ausentes:** 0

## Tratamento dos dados

O processo de tratamento foi dividido nas seguintes etapas:

1. Importação das bibliotecas;
2. Carregamento da base de dados;
3. Conhecimento da estrutura da base;
4. Verificação de valores ausentes;
5. Identificação de registros duplicados;
6. Análise das duplicidades;
7. Análise da RAIS negativa;
8. Análise dos vínculos empregatícios;
9. Validação dos códigos;
10. Validação dos estabelecimentos;
11. Definição dos critérios de limpeza;
12. Aplicação da limpeza;
13. Validação da base final;
14. Exportação da base limpa.

## Análise das duplicidades

Foram identificados **7.906 registros envolvidos em duplicidades exatas**, considerando todas as variáveis disponíveis na base.

A análise também identificou **42.362 registros únicos**. Caso todas as duplicidades exatas fossem removidas automaticamente, seriam eliminados **4.977 registros**.

Entretanto, a duplicidade das variáveis disponíveis não permite afirmar que os registros representam necessariamente o mesmo estabelecimento, pois a base analisada não apresenta um identificador único do estabelecimento.

Por esse motivo, as duplicidades foram identificadas e analisadas, mas não foram excluídas automaticamente.

Essa decisão evita a remoção indevida de registros que podem representar estabelecimentos distintos com características iguais nas variáveis disponíveis.

## Validação da RAIS negativa

Foi realizada uma verificação da relação entre o indicador de RAIS negativa e a quantidade de vínculos CLT.

Não foram identificados registros de RAIS negativa com quantidade de vínculos CLT superior a zero.

## Valores ausentes

A análise da base original não identificou valores ausentes nas variáveis analisadas.

O mesmo resultado foi confirmado na base final.

## Base final

Após a aplicação dos critérios de limpeza, a base final permaneceu com:

- **47.339 registros**;
- **24 variáveis originais**;
- **0 valores ausentes**.

As duplicidades exatas identificadas foram mantidas, pois não havia evidência suficiente para classificá-las como registros inválidos.

## Estrutura do repositório

```text
limpeza-googlecolab/
│
├── dados/
│   └── RAIS_2025_SJC_limpa.xlsx
│
├── notebooks/
│   └── RAIS_2025_limpeza.ipynb
│
└── README.md

Tecnologias utilizadas
Python
Google Colab
Pandas
NumPy
Microsoft Excel
GitHub
Resultado

O resultado do processo é uma base RAIS 2025 analisada e documentada, acompanhada do notebook contendo as etapas de carregamento, análise, tratamento, validação e exportação dos dados.

Observação metodológica

A manutenção das duplicidades exatas não significa que os dados estejam incorretos. Significa que, com as variáveis disponíveis na base analisada, não foi possível determinar com segurança que esses registros representavam duplicações indevidas.

A decisão de não excluir esses registros foi adotada para preservar a integridade da informação e evitar perdas de dados sem evidência suficiente.
