# Análise de Comportamento de Streaming de Música (Springfield vs. Shelbyville)

## 📌 Contexto e Objetivo
Este projeto analisa dados reais de reprodução de um serviço de streaming de música online (**65.079 registros iniciais**) para investigar padrões de consumo entre usuários de duas cidades: **Springfield** e **Shelbyville**[cite: 11].

**Hipótese testada:**
> *A atividade dos usuários é diferente dependendo do dia da semana e da cidade[cite: 11].*

---

## 🛠️ Etapas da Análise

### 1. Diagnóstico e Pré-processamento de Dados
- **Padronização de cabeçalhos:** Conversão de todas as colunas para letras minúsculas, remoção de espaços extras e aplicação de `snake_case` (`user_id`)[cite: 11].
- **Tratamento de valores ausentes:** Identificação de valores nulos em `track` (1.343), `artist` (7.567) e `genre` (1.198), preenchidos como `'unknown'` para preservar o volume total de reproduções por cidade e dia[cite: 11].
- **Limpeza de duplicados:** Remoção de **3.826 registros duplicados explícitos** e unificação de duplicados implícitos de gênero (`hip`, `hop` e `hip-hop` padronizados para `hiphop`)[cite: 11].

### 2. Análise Exploratória e Teste da Hipótese
Agrupamento e filtragem lógica utilizando **Python** e **Pandas** para comparar o volume de faixas reproduzidas às segundas, quartas e sextas-feiras nas duas cidades[cite: 11]:

| Dia da Semana | Springfield | Shelbyville | Total |
| :--- | :---: | :---: | :---: |
| **Segunda-feira (Monday)** | 15.740 | 5.614 | 21.354 |
| **Quarta-feira (Wednesday)** | 11.056 | 7.003 | 18.059 |
| **Sexta-feira (Friday)** | 15.945 | 5.895 | 21.840 |
| **Total por Cidade** | **42.741** | **18.512** | **61.253** |

---

## 💡 Principais Conclusões
- **Hipótese confirmada:** O comportamento de consumo varia significativamente conforme a cidade e o dia da semana[cite: 11].
- **Volume geral:** Springfield apresenta um volume de atividade aproximadamente **2,3 vezes maior** que Shelbyville (42.741 contra 18.512 reproduções)[cite: 11].
- **Padrão semanal oposto:** Enquanto Springfield atinge seus picos de consumo na **segunda-feira (15.740)** e na **sexta-feira (15.945)** com queda na quarta-feira, Shelbyville apresenta comportamento inverso, atingindo seu pico relativo justamente na **quarta-feira (7.003)**[cite: 11].

---

## 💻 Tecnologias e Estrutura
- **Python 3** & **Pandas** (limpeza, tratamento de nulos, agrupamento e filtragem lógica)[cite: 11]
- **Jupyter Notebook** (`music-streaming-hypothesis-analysis.ipynb`)
