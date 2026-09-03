# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href="https://www.fiap.com.br/">
<img src="https://raw.githubusercontent.com/agodoi/templateFiapVfinal/main/assets/logo-fiap.png" alt="FIAP" width="40%">
</a>
</p>

# CardioIA — A Nova Era da Cardiologia Inteligente

## Fase 1 — Batimentos de Dados

## Grupo CardioIA

## 👨‍🎓 Integrantes

* [CAUAN OTTO RODRIGUES SOUSA — RM567940](https://www.linkedin.com/in/cauanotto)
* [FERNANDO A. GURGEL — RM567606](https://www.linkedin.com/in/fernando-gurgel-75aa8369)
* [IRACI MONTEIRO SOUZA — RM567544](https://www.linkedin.com/in/iraci-souza-bab42034)
* [MARIA LUISA RODRIGUES NASCIMENTO — RM567659](https://www.linkedin.com/in/malu-rodrigues-bb756b271)
* [RAFAELA TORRES MARTINS — RM567735](https://www.linkedin.com/in/rafaela-torres222)

## 👩‍🏫 Professores

### Tutor

* [LEONARDO RUIZ ORABONA](https://br.linkedin.com/in/leonardoorabona)

### Coordenador

* [ANDRÉ GODOI](https://www.linkedin.com/in/andregodoichiovato)

---

## 📜 Descrição do projeto

O **CardioIA** é um projeto acadêmico que representa um ecossistema de cardiologia apoiado por Inteligência Artificial.

A **Fase 1 — Batimentos de Dados** tem como objetivo construir a base de dados necessária para as etapas futuras do projeto. Foram reunidas e organizadas três modalidades de dados relacionadas à saúde cardiovascular:

1. dados numéricos para análise estatística e Machine Learning;
2. textos médicos para Processamento de Linguagem Natural;
3. imagens de eletrocardiograma para Visão Computacional.

Além da coleta, a entrega documenta a origem, as características, as limitações, os possíveis usos em IA e os principais riscos de governança de cada conjunto.

> Este projeto possui finalidade exclusivamente acadêmica. Os dados, análises e futuros modelos não devem ser utilizados como diagnóstico, prescrição ou substituição da avaliação realizada por profissionais de saúde.

---

## ✅ Entregáveis preparados

| Modalidade       | Conteúdo preparado                                   |      Quantidade | Acesso                                                 |
| ---------------- | ---------------------------------------------------- | --------------: | ------------------------------------------------------ |
| Dados numéricos  | Amostra cardiovascular original e versão tratada     |   100 registros | [Abrir pasta](./data/numericos/)                       |
| Dados textuais   | Dois corpora baseados em diretrizes cardiovasculares |  2 arquivos TXT | [Abrir pasta](./docs/textos/)                          |
| Dados visuais    | Recortes de derivações de ECG                        | 108 imagens PNG | [Abrir imagens](https://github.com/fiap-ia-trabalho/2ano_cardioia-fase1-batimentos-de-dados/tree/fcb8a4d61d1a210cbb30bc8663c7c5be92b83a3d/assets/ecg/Images)                  |
| Catálogo visual  | Manifesto com metadados e hashes                     |   108 registros | [Abrir manifesto](./assets/ecg/manifest_ecg_108.csv)   |
| Validação visual | Relatório de integridade e distribuição              |     1 relatório | [Abrir relatório](./assets/ecg/RELATORIO_VALIDACAO.md) |

---

# 📊 Parte 1 — Dados Numéricos

## Fonte original

**Cardiovascular Disease Dataset — Kaggle**
Autora: Svetlana Ulianova
Fonte: https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

A fonte possui aproximadamente **70.000 registros**, 11 variáveis de entrada e uma variável-alvo chamada `cardio`. Segundo a descrição do dataset, os dados foram coletados durante exames médicos. Por esse motivo, são tratados neste projeto como dados reais e não sintéticos.

A licença aparece no Kaggle como **Unknown**. Portanto, não se presume autorização para uso comercial ou redistribuição irrestrita. A utilização nesta atividade é acadêmica, com atribuição da fonte e registro dessa limitação.

## Dataset preparado

Foi organizada uma amostra com **100 registros**, atendendo ao mínimo solicitado na atividade.

Arquivos disponíveis:

* [`cardio_train_amostra_100.csv`](./data/numericos/cardio_train_amostra_100.csv): amostra com os campos da estrutura original;
* [`cardio_train_amostra_100_preparada.csv`](./data/numericos/cardio_train_amostra_100_preparada.csv): versão tratada, com nomes mais legíveis;
* [`cardio_train_amostra_100_preparada.xlsx`](./data/numericos/cardio_train_amostra_100_preparada.xlsx): planilha compatível com Excel;
* [`dicionario_dados.csv`](./data/numericos/dicionario_dados.csv): explicação das variáveis.

Na versão preparada foram realizadas as seguintes transformações:

* conversão da idade de dias para anos;
* cálculo do Índice de Massa Corporal;
* tradução e padronização dos nomes das colunas;
* transformação dos códigos de colesterol e glicose em categorias legíveis;
* preservação do identificador original para rastreabilidade;
* manutenção da variável-alvo de doença cardiovascular.

## Variáveis e relevância

| Variável              | Relevância clínica e analítica                                      |
| --------------------- | ------------------------------------------------------------------- |
| Idade                 | Permite analisar variações do risco ao longo do ciclo de vida.      |
| Sexo                  | Possibilita avaliar diferenças de distribuição e potenciais vieses. |
| Altura e peso         | Permitem calcular medidas antropométricas.                          |
| IMC                   | Auxilia na análise de excesso de peso e risco cardiometabólico.     |
| Pressão sistólica     | Indicador importante para avaliação cardiovascular.                 |
| Pressão diastólica    | Complementa a análise da pressão arterial.                          |
| Colesterol            | Representa parte do perfil de risco cardiometabólico.               |
| Glicose               | Permite investigar associação com alterações metabólicas.           |
| Tabagismo             | Fator comportamental relevante para o risco cardiovascular.         |
| Consumo de álcool     | Variável comportamental para segmentação e análise.                 |
| Atividade física      | Pode representar um fator comportamental protetor.                  |
| Doença cardiovascular | Variável-alvo utilizada em futuras classificações.                  |

## Possíveis aplicações de IA

* classificação da presença ou ausência de doença cardiovascular;
* análise exploratória de fatores associados ao desfecho;
* agrupamento de perfis semelhantes de pacientes;
* detecção de outliers e medições inconsistentes;
* análise de importância das variáveis;
* desenvolvimento futuro de modelos de apoio à triagem.

## Limitações

A amostra local possui somente 100 registros e não representa toda a diversidade da base original. A fonte também não esclarece suficientemente país, instituição de origem, estratégia de amostragem e representatividade populacional.

Não se deve assumir que os dados representam a população brasileira. A codificação binária da variável sexo também limita análises mais amplas de diversidade.

Valores de pressão arterial, altura, peso e IMC devem passar por validação de faixas antes do treinamento de modelos.

---

# 📝 Parte 2 — Dados Textuais

Foram preparados dois arquivos TXT relacionados à saúde cardiovascular, baseados em diretrizes científicas brasileiras disponibilizadas pelo SciELO.

## Texto 1 — Hipertensão arterial

**Diretrizes Brasileiras de Hipertensão Arterial – 2020**

* Fonte: SciELO / Arquivos Brasileiros de Cardiologia
* Publicação: 2021
* DOI: 10.36660/abc.20201238
* URL: https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt
* Arquivo: [`texto_01_hipertensao_scielo.txt`](./docs/textos/texto_01_hipertensao_scielo.txt)

## Texto 2 — Síndrome coronariana crônica

**Diretriz de Síndrome Coronariana Crônica – 2025**

* Fonte: SciELO / Arquivos Brasileiros de Cardiologia
* DOI: 10.36660/abc.20250619
* URL: https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en
* Arquivo: [`texto_02_sindrome_coronariana_scielo.txt`](./docs/textos/texto_02_sindrome_coronariana_scielo.txt)

Os arquivos locais são corpora acadêmicos preparados a partir dos temas e conceitos das publicações. Eles preservam os metadados e a atribuição das fontes, mas não substituem a consulta às diretrizes originais.

## Possíveis aplicações de NLP

* reconhecimento de sintomas, doenças, exames e fatores de risco;
* identificação de entidades médicas;
* classificação de trechos por assunto;
* extração de palavras-chave;
* sumarização automática;
* análise de frequência e associação de termos;
* busca semântica;
* construção futura de chatbot educacional fundamentado em fontes;
* criação de bases de perguntas e respostas.

## Relevância

Textos médicos contêm relações, contexto e vocabulário especializado que não aparecem integralmente em bases numéricas. Sistemas de NLP podem organizar esse conhecimento e facilitar a recuperação de informações.

Entretanto, a data, a fonte, o contexto e a incerteza devem ser preservados. Respostas automáticas não podem ser apresentadas como recomendações clínicas individualizadas.

---

# 🫀 Parte 3 — Dados Visuais

## Fonte original

**ECG ROI Segmentation Dataset — Kaggle**
Autor: Gowri Shankar Penugonda
Fonte: https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped

Segundo o Data Card, a fonte contém recortes de derivações de eletrocardiograma e máscaras binárias produzidos por um pipeline de processamento relacionado ao PhysioNet 2025 Challenge.

As imagens são descritas neste projeto como **dados derivados e processados pela fonte**. Elas não foram criadas pelo grupo e não devem ser tratadas como exames clínicos brutos.

A licença aparece no Kaggle como **Unknown**. O conjunto é utilizado apenas no contexto acadêmico, mantendo a atribuição explícita.

## Dataset preparado

Foi preparada uma seleção com **108 imagens PNG**.

A seleção contém:

* nove identificadores de amostra;
* 12 derivações por identificador;
* nove imagens de cada derivação;
* 108 imagens no total;
* 108 arquivos válidos;
* 108 hashes únicos;
* nenhuma duplicata exata;
* nenhum arquivo vazio.

Derivações representadas:

`I`, `II`, `III`, `aVR`, `aVL`, `aVF`, `V1`, `V2`, `V3`, `V4`, `V5` e `V6`.

Arquivos da entrega:

* [108 imagens PNG](./assets/ecg/Images/)
* [Manifesto dos arquivos](./assets/ecg/manifest_ecg_108.csv)
* [Relatório de validação](./assets/ecg/RELATORIO_VALIDACAO.md)
* [Documentação do dataset visual](./assets/ecg/README.md)

## Possíveis aplicações de Visão Computacional

* segmentação do traçado de ECG;
* separação entre sinal, fundo e grade;
* detecção de linhas, curvas e bordas;
* identificação de imagens cortadas, desfocadas ou inclinadas;
* avaliação automática da qualidade da imagem;
* extração de características visuais;
* reconhecimento futuro de padrões, desde que existam rótulos clínicos confiáveis.

Uma possível aplicação seria a triagem técnica de exames. O sistema verificaria a qualidade da imagem e sinalizaria exames que precisem de revisão prioritária. A decisão permaneceria sob responsabilidade de profissionais de saúde.

## Limitação de representatividade

Os nove identificadores selecionados compartilham o identificador-base `1006427285` e diferem pelo sufixo de augmentação.

Portanto, as 108 imagens não representam 108 pacientes. Elas representam 108 arquivos correspondentes a derivações e augmentações relacionadas ao mesmo identificador-base.

Em futuros experimentos, treino, validação e teste deverão ser separados pelo identificador-base, evitando que variações relacionadas apareçam simultaneamente em conjuntos diferentes.

---

# 🔐 Governança, ética e viés

| Dimensão           | Risco                                      | Tratamento adotado ou recomendado                                      |
| ------------------ | ------------------------------------------ | ---------------------------------------------------------------------- |
| Proveniência       | Perda da origem do dado                    | Registro de URL, autor, arquivo e documentação.                        |
| Licença            | Uso incompatível com os termos             | Registro de licenças e indicação explícita quando forem desconhecidas. |
| Qualidade          | Outliers, arquivos inválidos ou duplicados | Validação de faixas, formatos, hashes e duplicatas.                    |
| Privacidade        | Identificação de pessoas                   | Não realizar tentativa de reidentificação e verificar metadados.       |
| Representatividade | Baixa diversidade populacional             | Registrar limitações e ampliar as fontes em etapas futuras.            |
| Vazamento de dados | Augmentações em treino e teste             | Separar conjuntos pelo identificador-base.                             |
| Viés demográfico   | Desempenho desigual entre grupos           | Avaliar métricas por idade, sexo e outros grupos disponíveis.          |
| Segurança clínica  | Resultado interpretado como diagnóstico    | Uso acadêmico, supervisão humana e comunicação das limitações.         |
| Atualização        | Conteúdo médico tornar-se desatualizado    | Manter título, ano, DOI, versão e data de acesso.                      |

Documentação complementar: [`FONTES_E_GOVERNANCA.md`](./FONTES_E_GOVERNANCA.md).

---

# 🔗 Datasets preparados pelo grupo

| Entregável                 | Link público                                             |
| -------------------------- | -------------------------------------------------------- |
| Dataset numérico preparado | [Acessar no GitHub](./data/numericos/)                   |
| Corpus textual para NLP    | [Acessar no GitHub](./docs/textos/)                      |
| Seleção com 108 imagens    | [Acessar no GitHub](./assets/ecg/Images/)                |
| Manifesto das imagens      | [Acessar no GitHub](./assets/ecg/manifest_ecg_108.csv)   |
| Validação das imagens      | [Acessar no GitHub](./assets/ecg/RELATORIO_VALIDACAO.md) |

# 🌐 Fontes originais

| Modalidade                       | Fonte                                                                               |
| -------------------------------- | ----------------------------------------------------------------------------------- |
| Dados numéricos                  | https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset            |
| Texto sobre hipertensão          | https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt                      |
| Texto sobre síndrome coronariana | https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en |
| Imagens de ECG                   | https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped                   |

---

## 📁 Estrutura do repositório

```text
2ano_cardioia-fase1-batimentos-de-dados/
├── README.md
├── FONTES_E_GOVERNANCA.md
├── data/
│   └── numericos/
│       ├── README.md
│       ├── cardio_train_amostra_100.csv
│       ├── cardio_train_amostra_100_preparada.csv
│       ├── cardio_train_amostra_100_preparada.xlsx
│       └── dicionario_dados.csv
├── docs/
│   └── textos/
│       ├── texto_01_hipertensao_scielo.txt
│       └── texto_02_sindrome_coronariana_scielo.txt
└── assets/
    └── ecg/
        ├── README.md
        ├── RELATORIO_VALIDACAO.md
        ├── manifest_ecg_108.csv
        └── Images/
            ├── ecg_001_1006427285-0001_I.png
            ├── ...
            └── ecg_108_1006427285-0012_aVR.png
```

---

## 🔧 Como acessar e reproduzir

### Opção 1 — Download pelo GitHub

1. Clique em **Code**.
2. Selecione **Download ZIP**.
3. Descompacte o arquivo.
4. Abra as pastas `data`, `docs` e `assets`.

### Opção 2 — Clonar o repositório

```bash
git clone https://github.com/fiap-ia-trabalho/2ano_cardioia-fase1-batimentos-de-dados.git
cd 2ano_cardioia-fase1-batimentos-de-dados
```

### Leitura do dataset preparado em Python

```python
import pandas as pd

df = pd.read_csv(
    "data/numericos/cardio_train_amostra_100_preparada.csv",
    encoding="utf-8-sig"
)

print(df.head())
print(df.shape)
print(df.info())
```

### Leitura dos textos

```python
from pathlib import Path

pasta = Path("docs/textos")

for arquivo in pasta.glob("*.txt"):
    texto = arquivo.read_text(encoding="utf-8")
    print(arquivo.name, len(texto))
```

### Contagem das imagens

```python
from pathlib import Path

imagens = list(Path("assets/ecg/Images").glob("*.png"))
print(f"Quantidade de imagens: {len(imagens)}")
```

O resultado esperado é:

```text
Quantidade de imagens: 108
```

---

## 🎯 Conclusão

A Fase 1 do CardioIA reúne dados numéricos, textuais e visuais capazes de apoiar etapas futuras de Machine Learning, NLP e Visão Computacional.

A entrega também demonstra que a construção de uma solução de IA em saúde exige mais do que reunir arquivos. É necessário conhecer a origem dos dados, documentar transformações, avaliar qualidade, respeitar licenças, reconhecer vieses e limitar interpretações clínicas indevidas.

---

## 🗃 Histórico de versões

### 1.0.0 — Fase 1

* organização do dataset cardiovascular com 100 registros;
* criação de versão preparada em CSV e Excel;
* elaboração do dicionário de dados;
* preparação de dois corpora textuais;
* seleção e validação de 108 imagens de ECG;
* criação do manifesto das imagens;
* documentação de governança, ética, limitações e aplicações futuras.

---

## 📚 Referências

* ULIANOVA, Svetlana. *Cardiovascular Disease Dataset*. Kaggle. Disponível em: https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset.
* BARROSO, W. K. S. et al. *Diretrizes Brasileiras de Hipertensão Arterial – 2020*. Arquivos Brasileiros de Cardiologia. DOI: 10.36660/abc.20201238.
* CESAR, L. A. M. et al. *Diretriz de Síndrome Coronariana Crônica – 2025*. Arquivos Brasileiros de Cardiologia. DOI: 10.36660/abc.20250619.
* PENUGONDA, Gowri Shankar. *ECG ROI Segmentation Dataset*. Kaggle. Disponível em: https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped.

---

## 📋 Licença e responsabilidade

O conteúdo produzido pelo grupo é destinado a fins acadêmicos.

As fontes externas não são relicenciadas por este projeto. Cada base e publicação conserva seus próprios termos de uso. Quando a licença não foi informada pela fonte, essa condição foi registrada expressamente.

Nenhum conteúdo deste repositório deve ser utilizado para diagnóstico ou tomada de decisão clínica.
