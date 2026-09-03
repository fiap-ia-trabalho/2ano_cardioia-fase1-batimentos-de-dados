# Fontes, rastreabilidade e governança

Este documento registra a procedência, a preparação, as limitações e as condições de uso das três modalidades de dados utilizadas na Fase 1 do CardioIA.

## 1. Dados numéricos

### Identificação

* **Nome:** Cardiovascular Disease Dataset
* **Autora:** Svetlana Ulianova
* **Plataforma:** Kaggle
* **URL:** https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
* **Natureza declarada:** dados coletados durante exames médicos
* **Classificação adotada:** dados reais, não sintéticos
* **Tamanho informado:** aproximadamente 70.000 registros
* **Licença apresentada no Kaggle:** Unknown

### Preparação local

O repositório contém uma amostra com 100 registros, uma versão tratada em CSV, uma versão Excel e um dicionário de dados.

Na preparação foram realizadas:

* conversão da idade de dias para anos;
* criação do IMC a partir de peso e altura;
* tradução e padronização dos nomes das colunas;
* categorização textual de colesterol e glicose;
* preservação do identificador original;
* manutenção da variável-alvo cardiovascular.

### Rastreabilidade e limitações

A amostra local foi conferida a partir de uma cópia pública que referencia o mesmo dataset e mantém sua estrutura de variáveis. A página oficial do Kaggle permanece como referência canônica.

Essa condição limita a cadeia de custódia da amostra e deve ser considerada na interpretação dos dados, mas não altera a finalidade acadêmica desta entrega.

A fonte não esclarece suficientemente país, instituição responsável, método de amostragem ou representatividade populacional. Portanto, os registros não devem ser considerados representativos da população brasileira.

A codificação binária da variável sexo também restringe análises mais amplas de diversidade.

Como a licença aparece como Unknown, não se presume autorização para exploração comercial ou redistribuição irrestrita.

### Riscos de qualidade

Antes de qualquer modelagem devem ser avaliados:

* valores fisiologicamente improváveis;
* pressão sistólica menor que a diastólica;
* alturas e pesos extremos;
* IMC fora de faixas plausíveis;
* duplicidades;
* dados ausentes;
* desequilíbrio da variável-alvo;
* diferenças de desempenho por idade e sexo.

---

## 2. Dados textuais

### Fonte 1

* **Título:** Diretrizes Brasileiras de Hipertensão Arterial – 2020
* **Fonte:** SciELO / Arquivos Brasileiros de Cardiologia
* **Publicação:** 2021
* **DOI:** 10.36660/abc.20201238
* **URL:** https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt
* **Licença informada:** Creative Commons Attribution

### Fonte 2

* **Título:** Diretriz de Síndrome Coronariana Crônica – 2025
* **Fonte:** SciELO / Arquivos Brasileiros de Cardiologia
* **DOI:** 10.36660/abc.20250619
* **URL:** https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en
* **Licença informada:** Creative Commons Attribution

### Preparação local

Foram produzidos dois corpora acadêmicos em formato TXT. Eles organizam, em linguagem própria e parafraseada, conceitos relacionados aos temas das publicações.

Os arquivos preservam título, fonte, DOI, URL, finalidade e data de acesso. Eles não substituem as diretrizes originais e não reproduzem integralmente as publicações.

### Governança dos textos

Modelos de NLP devem preservar:

* identificação da fonte;
* data e versão do documento;
* contexto do trecho recuperado;
* diferença entre informação educacional e orientação clínica;
* incerteza e limitações;
* rastreabilidade das respostas;
* supervisão humana.

As respostas de um futuro chatbot não poderão ser apresentadas como diagnóstico, prescrição ou recomendação personalizada.

---

## 3. Dados visuais

### Identificação

* **Nome:** ECG ROI Segmentation Dataset
* **Autor:** Gowri Shankar Penugonda
* **Plataforma:** Kaggle
* **URL:** https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped
* **Versão consultada:** 5
* **Data de acesso:** 03/09/2026
* **Licença apresentada no Kaggle:** Unknown
* **Natureza:** imagens derivadas e processadas pela fonte
* **Classificação adotada:** não geradas pelo grupo e não tratadas como exames clínicos brutos

### Seleção preparada

Foram organizadas 108 imagens PNG:

* nove identificadores de amostra;
* 12 derivações por identificador;
* nove imagens por derivação;
* 108 imagens válidas;
* 108 hashes únicos;
* nenhuma duplicata exata;
* nenhum arquivo vazio.

O arquivo `manifest_ecg_108.csv` registra:

* sequência;
* nome do arquivo;
* identificador da amostra;
* identificador-base;
* augmentação;
* derivação;
* formato;
* dimensões;
* canais;
* tamanho;
* hash SHA-256;
* natureza do dado.

### Representatividade

Os nove identificadores compartilham o identificador-base `1006427285`. Eles correspondem a augmentações relacionadas, e não a nove pacientes independentes.

O conjunto comprova a coleta e organização de mais de 100 imagens, mas possui baixa diversidade clínica.

Em um modelo futuro, a separação entre treino, validação e teste deverá ocorrer pelo identificador-base. Isso evita vazamento de dados entre imagens relacionadas.

A seleção não possui rótulos diagnósticos comprovados. Por isso, nenhuma imagem deve ser classificada como normal, arritmia, infarto ou outra condição clínica sem evidência adicional.

### Privacidade e uso

Não foi realizada tentativa de identificar pessoas ou combinar os identificadores com outras bases.

Como a licença aparece como Unknown, o material é mantido exclusivamente para a atividade acadêmica, com atribuição explícita e sem alegação de direito comercial.

---

## 4. Matriz geral de riscos

| Risco                        | Impacto                                         | Tratamento                                                  |
| ---------------------------- | ----------------------------------------------- | ----------------------------------------------------------- |
| Licença desconhecida         | Uso incompatível com os termos                  | Limitar ao contexto acadêmico e manter atribuição.          |
| Falta de representatividade  | Modelo com baixa capacidade de generalização    | Ampliar fontes, grupos e identificadores.                   |
| Outliers numéricos           | Previsões distorcidas                           | Validar faixas e investigar casos extremos.                 |
| Vazamento entre augmentações | Métricas artificialmente elevadas               | Dividir os dados pelo identificador-base.                   |
| Desatualização dos textos    | Informação incompatível com evidências recentes | Registrar ano, DOI, fonte e versão.                         |
| Reidentificação              | Violação de privacidade                         | Remover metadados identificáveis e proibir reidentificação. |
| Automação clínica indevida   | Risco à saúde                                   | Supervisão humana e finalidade não diagnóstica.             |
| Viés demográfico             | Desempenho desigual                             | Avaliar métricas segmentadas quando possível.               |

## 5. Princípios adotados

* transparência sobre origem e limitações;
* rastreabilidade dos arquivos;
* documentação das transformações;
* respeito às licenças;
* minimização de dados;
* prevenção de reidentificação;
* avaliação de qualidade antes da modelagem;
* análise de viés;
* supervisão humana;
* uso exclusivamente acadêmico e não diagnóstico.
