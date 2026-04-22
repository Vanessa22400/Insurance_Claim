# Insurance Claim Analytics: Fatores de Custo, Segmentação de Risco e Modelagem Preditiva  
Análise de custos em saúde e identificação de perfis com maior probabilidade de gerar sinistros elevados por meio de análise de dados, inferência causal e machine learning.

Também foi desenvolvida uma aplicação interativa baseada neste projeto utilizando Streamlit:  
https://github.com/Vanessa22400/insurance_risk_prediction_simulator/tree/main

Base de dados: Health Insurance Dataset (1.338 indivíduos)  
Técnicas utilizadas: SQL, Análise Exploratória de Dados (EDA), segmentação de risco, K-Means, inferência causal (Propensity Score Matching), modelos preditivos (Regressão Linear e Random Forest), classificação e ajuste de threshold.  

Principal insight: o tabagismo é o principal fator de custo, elevando os gastos em aproximadamente US$ 23.500 por pessoa ao ano (cerca de 4 vezes mais), além de impactar diretamente o risco de sinistros de alto valor.

---

## Contexto do Projeto

Este projeto explora como a análise de dados pode apoiar a tomada de decisão no setor de seguros, especialmente na identificação de fatores que influenciam custos e na caracterização de perfis de risco.

Ele faz parte de uma análise mais ampla. Como extensão, foi desenvolvido um projeto complementar focado em estratégias preventivas e desfechos de saúde:  
https://github.com/Vanessa22400/Preventive_Health_Analytics

---

## Aplicação Interativa

Para tornar a análise mais acessível, foi criada uma aplicação interativa que permite simular diferentes perfis e avaliar o impacto de variáveis como tabagismo, IMC e idade sobre:

- custos de saúde  
- nível de risco  
- possíveis implicações de longo prazo  

Acesse:  
https://github.com/Vanessa22400/insurance_risk_prediction_simulator/tree/main

---

## Contexto de Negócio

No setor de seguros, compreender os fatores que direcionam custos e a concentração de risco é fundamental para:

- definição de preços  
- gestão de carteira  
- sustentabilidade financeira  

O projeto busca responder questões como:

- Quais variáveis mais influenciam os custos em saúde?  
- Como esses custos se distribuem entre os indivíduos?  
- Quem tem maior probabilidade de gerar sinistros elevados?  
- Como modelos analíticos podem apoiar decisões mais informadas?  

---

## Dataset

Fonte:  
https://www.kaggle.com/datasets/mirichoi0218/insurance

- 1.338 indivíduos  
- 7 variáveis  
- sem valores ausentes  
- dados anonimizados  

Variáveis principais:

`age`, `sex`, `bmi`, `children`, `smoker`, `region`, `charges`

Os custos variam de aproximadamente US$ 1.000 até mais de US$ 63.000, indicando a presença de um grupo com concentração de alto custo.

---

## Pipeline Analítico

1. Exploração inicial com SQL  
2. Análise Exploratória de Dados (EDA)  
3. Construção de score de risco  
4. Segmentação de clientes (clustering)  
5. Inferência causal  
6. Modelagem preditiva (regressão)  
7. Modelagem de risco (classificação)  
8. Ajuste de threshold e análise de decisão  

---

## Principais Análises

### Análise Exploratória e SQL

A análise inicial evidencia diferenças claras entre grupos:

- fumantes apresentam custos significativamente mais altos  
- custos aumentam com a idade  
- IMC elevado está associado a maiores despesas  
- a combinação de fatores de risco intensifica os custos  

---

### Segmentação de Risco

A construção de um score de risco mostra que:

- os fatores atuam de forma acumulativa  
- o aumento do risco está associado a crescimento não linear dos custos  
- um grupo reduzido concentra a maior parte das despesas  

---

### Segmentação de Clientes

A aplicação de K-Means permitiu identificar perfis distintos:

- jovens com baixo custo  
- famílias  
- indivíduos mais velhos  
- grupo de alto risco associado a estilo de vida  

Cada segmento apresenta padrões próprios de custo e risco.

---

### Inferência Causal

Por meio de Propensity Score Matching:

- o tabagismo aumenta os custos em cerca de US$ 23.500 por ano  
- o efeito permanece significativo mesmo após controle de outras variáveis  

---

### Modelagem Preditiva

Modelos utilizados:

- Regressão Linear (R² aproximado de 0.78)  
- Random Forest (R² aproximado de 0.86)  

Principais variáveis explicativas:

- tabagismo  
- IMC  
- idade  

---

### Modelagem de Risco

Foi construída uma variável binária para identificar indivíduos com maior probabilidade de gerar sinistros elevados.

Modelos utilizados:

- Regressão Logística  
- Random Forest Classifier  

Resultados indicam que:

- o Random Forest apresentou maior precisão (aproximadamente 0.96)  
- os modelos conseguem identificar indivíduos de alto risco com boa consistência  

---

### Ajuste de Threshold

Além da acurácia, foram avaliados diferentes thresholds de decisão.

Principais observações:

- a redução do threshold não aumentou o recall (mantido em torno de 0.79)  
- houve queda na precisão (de 0.96 para 0.92), com aumento de falsos positivos  

O threshold padrão (0.5) apresentou o melhor equilíbrio entre precisão e recall.

---

## Principais Insights

- o tabagismo é o principal direcionador de custos  
- fatores de risco se acumulam e ampliam os gastos  
- uma parcela reduzida da população concentra grande parte dos custos  
- modelos preditivos conseguem estimar custos e identificar risco com boa performance  
- a aplicação dos modelos é tão relevante quanto sua construção  

---

## Aplicações no Negócio

- estimativa mais precisa de custos  
- melhor entendimento da concentração de risco  
- identificação de perfis com alto potencial de sinistro  
- apoio à tomada de decisão orientada por dados  

---

## Limitações

- base de dados relativamente pequena  
- número limitado de variáveis  
- ausência de dados longitudinais  

---

## Próximos Passos

- testar modelos adicionais de machine learning  
- utilizar bases mais complexas  
- desenvolver visualizações interativas mais avançadas  
- explorar aplicações práticas no contexto de seguros  

---

## Estrutura do Repositório

```
.
├── data
│ └── insurance.csv
├── notebooks
│ └── Insurance_Risk_Analytics.ipynb
├── images
│ └── Healthcare_Cost_Dashboard.png
├── requirements.txt
└── README.md
```


---

## Conclusão

O projeto demonstra como a combinação de análise exploratória, segmentação, inferência causal e machine learning pode apoiar a identificação e gestão de sinistros de alto custo.

A abordagem permite compreender os principais fatores que direcionam despesas, quantificar seus impactos e transformar esses achados em suporte concreto para decisões mais estruturadas no setor de seguros.

