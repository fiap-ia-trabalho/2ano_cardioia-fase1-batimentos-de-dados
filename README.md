# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href="https://www.fiap.com.br/"><img src="https://raw.githubusercontent.com/agodoi/templateFiapVfinal/main/assets/logo-fiap.png" alt="FIAP" border="0" width="40%" height="40%"></a>
</p>

<br>

# CardioIA — A Nova Era da Cardiologia Inteligente

## Fase 1 — Batimentos de Dados

## Grupo CardioIA

## 👨‍🎓 Integrantes
- [CAUAN OTTO RODRIGUES SOUSA (RM567940)](https://www.linkedin.com/in/cauanotto)
- [FERNANDO A GURGEL (RM567606)](https://www.linkedin.com/in/fernando-gurgel-75aa8369)
- [IRACI MONTEIRO SOUZA (RM567544)](https://www.linkedin.com/in/iraci-souza-bab42034)
- [MARIA LUISA RODRIGUES NASCIMENTO (RM567659)](https://www.linkedin.com/in/malu-rodrigues-bb756b271)
- [RAFAELA TORRES MARTINS (RM567735)](https://www.linkedin.com/in/rafaela-torres222)

## 👩‍🏫 Professores
### Tutor
- [LEONARDO RUIZ ORABONA](https://br.linkedin.com/in/leonardoorabona)

### Coordenador
- [ANDRÉ GODOI](https://www.linkedin.com/in/andregodoichiovato)

---

## 📜 Descrição

O **CardioIA** é um projeto acadêmico que simula o ecossistema de uma cardiologia moderna apoiada por Inteligência Artificial. Na **Fase 1 — Batimentos de Dados**, o objetivo é construir uma base confiável para as etapas seguintes, reunindo três modalidades de dados: **numéricos**, **textuais** e **visuais**.

A seleção foi refeita utilizando fontes públicas indicadas pelo grupo: um dataset cardiovascular do Kaggle, duas diretrizes médicas do SciELO e uma base de imagens de ECG do Kaggle. Além da coleta, esta entrega registra origem, formato, possíveis usos em IA e riscos de governança, qualidade e viés.

> **Importante:** este é um projeto acadêmico. Nenhum dado, análise ou futuro modelo do CardioIA deve ser interpretado como diagnóstico, recomendação ou substituto de avaliação médica.

---

# 📊 Parte 1 — Dados Numéricos (IoT / Machine Learning)

### Fonte escolhida
**Kaggle — Cardiovascular Disease dataset, Svetlana Ulianova**  
https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

A fonte contém **70.000 registros**, com 11 variáveis de entrada e uma variável-alvo (`cardio`). Os valores foram coletados no momento de exame médico, portanto esta base é tratada no projeto como **real, não sintética**. O Kaggle informa a licença como **Unknown**, o que exige cautela em qualquer redistribuição além do contexto acadêmico.

Para a entrega, incluímos uma **amostra de 100 registros**, atendendo ao mínimo solicitado, e uma versão preparada com nomes mais legíveis, idade derivada em anos e IMC calculado.

**Rastreabilidade da amostra local:** a fonte oficial continua sendo o Kaggle. Para viabilizar a preparação técnica neste ambiente, os 100 registros locais foram conferidos a partir de um espelho público do arquivo `cardio_train.csv` que referencia o mesmo dataset. Em uma cadeia de custódia estrita, recomenda-se ao grupo comparar/substituir a amostra pelo arquivo baixado diretamente do Kaggle antes da submissão final.

### Principais variáveis

| Variável | Papel no projeto | Relevância clínica/analítica |
|---|---|---|
| Idade | Fator objetivo | Risco cardiovascular varia ao longo do ciclo de vida. |
| Sexo | Fator demográfico | Permite avaliar diferenças de distribuição e possíveis vieses. |
| Pressão sistólica/diastólica | Exame | Indicadores centrais para avaliação de risco cardiovascular. |
| Colesterol | Exame | Ajuda a representar perfil de risco cardiometabólico. |
| Glicose | Exame | Permite investigar associação com risco metabólico/cardiovascular. |
| Peso, altura e IMC | Antropometria | Úteis na análise de excesso de peso e estratificação populacional. |
| Tabagismo | Comportamental | Fator de risco relevante e útil para segmentação de perfis. |
| Atividade física | Comportamental | Pode ser explorada como variável protetora/comportamental. |
| `cardio` | Alvo | Indica presença/ausência de doença cardiovascular no dataset. |

### Arquivos preparados
- `data/cardio_train_amostra_100.csv` — amostra de 100 registros com os campos originais.
- `data/cardio_train_amostra_100_preparada.csv` — versão tratada e legível.
- `data/cardio_train_amostra_100_preparada.xlsx` — planilha com resumo e dicionário.
- `data/dicionario_dados.csv` — descrição das variáveis.

### Possíveis aplicações em IA
- Classificação supervisionada da variável `cardio`.
- Análise exploratória de fatores associados ao desfecho.
- Clusterização de perfis de pacientes.
- Detecção de outliers e inconsistências de medição.
- Futuras integrações com dados de sensores e monitoramento.

### Limitações
A base **não contém** sintomas, frequência cardíaca ou histórico familiar, que também seriam úteis ao CardioIA. Além disso, antes do treinamento será necessário validar outliers e medições fisiologicamente improváveis, principalmente nas variáveis de pressão arterial.

---

# 📝 Parte 2 — Dados Textuais (NLP)

Foram selecionadas duas diretrizes científicas brasileiras publicadas nos **Arquivos Brasileiros de Cardiologia/SciELO**, ambas disponibilizadas como acesso aberto sob licença Creative Commons Attribution.

### Texto 1 — Hipertensão arterial
**Diretrizes Brasileiras de Hipertensão Arterial – 2020**  
https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt

Arquivo preparado: `docs/texto_01_hipertensao_scielo.txt`

### Texto 2 — Síndrome coronariana crônica
**Diretriz de Síndrome Coronariana Crônica – 2025**  
https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en

Arquivo preparado: `docs/texto_02_sindrome_coronariana_scielo.txt`

Os arquivos locais são **corpora resumidos e parafraseados**; os artigos integrais permanecem nos links oficiais.

### Como explorar com NLP
- **Reconhecimento de entidades (NER):** sintomas, exames, doenças, medicamentos e fatores de risco.
- **Extração de sintomas:** localizar descrições de dor torácica, dispneia e outras manifestações.
- **Classificação de tópicos:** prevenção, diagnóstico, fatores de risco, exames e tratamento.
- **Busca semântica:** recuperar trechos relacionados a uma pergunta clínica ou tema.
- **Sumarização:** produzir resumos de seções extensas para apoio educacional.
- **Chatbots/agentes:** construir respostas baseadas em fontes controladas, com citação e limites de segurança.

### Relevância
Textos médicos oferecem vocabulário especializado e relações semânticas que dados tabulares não capturam. Em saúde, porém, respostas automatizadas devem preservar a fonte, data, contexto e incerteza, evitando transformar conteúdo educacional em recomendação clínica individual.

---

# 🫀 Parte 3 — Dados Visuais (Visão Computacional)

### Fonte escolhida
**Kaggle — ECG ROI Segmentation Dataset**  
https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped

A atividade solicita **no mínimo 100 imagens `.jpg` ou `.png`** de exame cardiológico. Para esta entrega, o conjunto completo permanece no Kaggle e o repositório registra a fonte, os requisitos e o plano de uso em `assets/ecg/`.

### Possíveis aplicações em Visão Computacional
- Pré-processamento e normalização de imagens de ECG.
- Segmentação de regiões de interesse (ROI).
- Detecção de bordas, linhas e padrões visuais.
- Extração de características para comparação entre exames.
- Classificação/reconhecimento de padrões, desde que os rótulos da fonte sejam adequados e validados.

### Governança específica da base visual
Antes da submissão final, o grupo deve confirmar no Data Card do Kaggle:
1. quantidade de imagens disponíveis e formato;
2. licença/termos de uso;
3. origem **real ou sintética**;
4. classes e distribuição dos rótulos;
5. ausência de identificadores de pacientes em pixels, nomes de arquivos ou metadados.

Não foi atribuída uma origem real/sintética sem confirmação documental, evitando registrar uma informação não comprovada.

---

# 🔐 Governança de Dados, Ética e Viés

A Fase 1 não termina na coleta: a qualidade da futura IA dependerá da qualidade e da governança das fontes.

| Dimensão | Risco | Tratamento proposto |
|---|---|---|
| Proveniência | Perder a origem do dado | Manter URL, autor/fonte e documentação de cada base. |
| Licença | Uso incompatível com os termos | Registrar licença; não presumir permissão quando ela não é informada. |
| Qualidade | Outliers e erros de medição | Validação de faixas, duplicatas e consistência antes de modelar. |
| Privacidade | Identificação em exames/imagens | Verificar metadados e sobreposições; anonimizar quando necessário. |
| Viés demográfico | Performance desigual por grupos | Medir distribuição e métricas segmentadas por sexo/faixa etária. |
| Viés de fonte | Diretrizes não representam todo contexto clínico | Manter data, fonte e escopo; evitar generalização indevida. |
| Segurança clínica | Modelo interpretado como diagnóstico | Restringir uso ao contexto acadêmico e exigir supervisão humana. |

Detalhes adicionais: [`FONTES_E_GOVERNANCA.md`](FONTES_E_GOVERNANCA.md).

---

## 🔗 Links públicos para os conjuntos completos

| Tipo | Fonte pública |
|---|---|
| Numérico | https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset |
| Texto 1 | https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt |
| Texto 2 | https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en |
| Imagens ECG | https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped |

> Se o tutor exigir especificamente **Google Drive ou OneDrive**, basta subir as mesmas bases e substituir esta tabela pelos links de compartilhamento público. O enunciado também admite outro serviço de armazenamento público.

---

## 📁 Estrutura de pastas

```text
CardioIA_Fase1_Repositorio_Novas_Bases/
├── README.md
├── FONTES_E_GOVERNANCA.md
├── data/
│   ├── cardio_train_amostra_100.csv
│   ├── cardio_train_amostra_100_preparada.csv
│   ├── cardio_train_amostra_100_preparada.xlsx
│   └── dicionario_dados.csv
├── docs/
│   ├── texto_01_hipertensao_scielo.txt
│   ├── texto_02_sindrome_coronariana_scielo.txt
├── assets/
    └── ecg/
       ├── README.md
       └── manifest_ecg_dataset.csv

```

---

## 🔧 Como executar / reproduzir

Esta fase é predominantemente de **coleta, preparação e documentação de dados**. Para inspecionar os dados numéricos:

1. Baixe ou clone o repositório.
2. Abra `data/cardio_train_amostra_100_preparada.xlsx` no Excel ou equivalente; ou use o CSV em Python/Pandas.
3. Consulte `data/dicionario_dados.csv` para entender as variáveis.
4. Abra os arquivos `.txt` da pasta `docs` para os experimentos de NLP.
5. Para experimentos visuais, acesse a fonte do Kaggle indicada em `assets/ecg/README.md` e prepare uma seleção de pelo menos 100 imagens conforme os termos da base.

Exemplo de carregamento do CSV em Python:

```python
import pandas as pd

df = pd.read_csv(
    "data/cardio_train_amostra_100_preparada.csv",
    encoding="utf-8-sig"
)
print(df.head())
```

---

## 🗃 Histórico de lançamentos

- **1.0.0 — Fase 1**
  - Dataset numérico real do Kaggle com amostra preparada de 100 registros.
  - Dois corpora textuais baseados em diretrizes SciELO.
  - Base visual de ECG referenciada via Kaggle.
  - Inclusão de documentação de governança e rastreabilidade.

---

## 📚 Referências principais

- ULIANOVA, Svetlana. *Cardiovascular Disease dataset*. Kaggle. https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
- BARROSO, W. K. S. et al. *Diretrizes Brasileiras de Hipertensão Arterial – 2020*. Arquivos Brasileiros de Cardiologia. DOI: 10.36660/abc.20201238.
- CESAR, L. A. M. et al. *Diretriz de Síndrome Coronariana Crônica – 2025*. Arquivos Brasileiros de Cardiologia. DOI: 10.36660/abc.20250619.
- *ECG ROI Segmentation Dataset*. Kaggle. https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped

---

## 📋 Licença

O conteúdo autoral deste repositório (documentação e scripts próprios, quando aplicável) é disponibilizado para fins acadêmicos. **As bases externas não são relicenciadas por este projeto**: cada dataset/artigo mantém seus próprios termos e licenças. 
