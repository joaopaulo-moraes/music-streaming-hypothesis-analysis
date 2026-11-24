# Análise de Consumo de Streaming: Springfield vs. Shelbyville

Neste projeto, analisei uma base com 65.079 registros de um serviço de streaming de música para comparar o comportamento dos usuários em duas cidades: **Springfield** e **Shelbyville**[cite: 4].

O objetivo foi validar a seguinte hipótese: **a atividade dos usuários muda conforme o dia da semana e a cidade[cite: 4].**

## O que foi feito nos dados

Antes de analisar os números, precisei limpar e padronizar a base original utilizando **Python** e **Pandas**[cite: 4]:

* **Padronização das colunas:** Coloquei todos os nomes em minúsculo, removi espaços em branco extras e ajustei `userID` para `user_id`[cite: 4].
* **Valores ausentes:** Preenchi os dados faltantes nas colunas `track` (1.343), `artist` (7.567) e `genre` (1.198) com `'unknown'` para não perder o volume real de reproduções na contagem por cidade[cite: 4].
* **Duplicados:** Excluí 3.826 linhas duplicadas e unifiquei variações de escrita do gênero hip-hop (`hip`, `hop` e `hip-hop` viraram `hiphop`)[cite: 4].

## Resultados encontrados

Após a limpeza, restaram 61.253 registros válidos. Agrupando os dados por cidade e dia da semana (segunda, quarta e sexta-feira), o volume de músicas tocadas ficou distribuído assim[cite: 4]:

| Dia da Semana | Springfield | Shelbyville | Total |
| :--- | :---: | :---: | :---: |
| Segunda-feira | 15.740 | 5.614 | 21.354 |
| Quarta-feira | 11.056 | 7.003 | 18.059 |
| Sexta-feira | 15.945 | 5.895 | 21.840 |
| **Total** | **42.741** | **18.512** | **61.253** |

## Conclusão

A hipótese foi confirmada, mas os dados revelaram dois comportamentos bem distintos[cite: 4]:

1. **Diferença de escala:** Springfield concentra cerca de 2,3 vezes mais reproduções do que Shelbyville no geral[cite: 4].
2. **Inversão durante a semana:** Em Springfield, o pico de uso acontece na segunda e na sexta-feira, com uma queda forte na quarta-feira[cite: 4]. Em Shelbyville acontece o oposto — o maior pico relativo de atividade da cidade ocorre justamente na quarta-feira (7.003 reproduções)[cite: 4].

## Arquivos e Ferramentas
* `music-streaming-hypothesis-analysis.ipynb`: Notebook completo com o código da limpeza e das consultas.
* **Stack:** Python 3, Pandas e Jupyter Notebook[cite: 4].
