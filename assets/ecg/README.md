# Dataset visual — ECG ROI Segmentation Dataset

## Resumo

Esta pasta contém uma seleção acadêmica de **108 imagens de ECG em formato PNG**, preparada para a Parte 3 — Dados Visuais da Fase 1 do CardioIA.

A seleção supera o mínimo de 100 imagens e apresenta:

* nove identificadores de amostra;
* 12 derivações por identificador;
* nove imagens por derivação;
* 108 imagens no total;
* 108 arquivos PNG válidos;
* 108 hashes únicos;
* nenhuma duplicata exata;
* nenhum arquivo vazio.

As máscaras de segmentação da fonte não foram incluídas na contagem.

## Fonte original

* **Nome:** ECG ROI Segmentation Dataset
* **Autor:** Gowri Shankar Penugonda
* **Plataforma:** Kaggle
* **URL:** https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped
* **Versão consultada:** 5
* **Data de acesso:** 03/09/2026
* **Licença apresentada pelo Kaggle:** Unknown

Segundo o Data Card, a fonte reúne recortes de derivações de ECG e máscaras binárias alinhadas. O conjunto foi produzido por um pipeline de processamento relacionado ao PhysioNet 2025 Challenge.

As imagens são classificadas neste projeto como dados derivados e processados pela fonte. Elas não foram geradas pelo grupo e não são apresentadas como exames clínicos brutos.

## Critério de seleção

Foram selecionados nove identificadores:

* `1006427285-0001`
* `1006427285-0003`
* `1006427285-0004`
* `1006427285-0005`
* `1006427285-0006`
* `1006427285-0009`
* `1006427285-0010`
* `1006427285-0011`
* `1006427285-0012`

Para cada identificador foram reunidas as 12 derivações:

* I;
* II;
* III;
* aVR;
* aVL;
* aVF;
* V1;
* V2;
* V3;
* V4;
* V5;
* V6.

## Estrutura

```text
assets/ecg/
├── README.md
├── RELATORIO_VALIDACAO.md
├── manifest_ecg_108.csv
└── images/
    ├── ecg_001_1006427285-0001_I.png
    ├── ...
    └── ecg_108_1006427285-0012_aVR.png
```

O padrão dos nomes é:

```text
ecg_NNN_SAMPLEID_DERIVACAO.png
```

## Integridade

O arquivo `manifest_ecg_108.csv` registra os metadados de cada imagem, incluindo nome, identificador, augmentação, derivação, dimensões, tamanho e hash SHA-256.

O relatório `RELATORIO_VALIDACAO.md` apresenta a contagem e a distribuição dos arquivos.

Resultado da validação:

* quantidade total: 108;
* arquivos inválidos: zero;
* arquivos vazios: zero;
* hashes únicos: 108;
* duplicatas exatas: zero;
* derivações representadas: 12;
* imagens por derivação: nove.

## Aplicações de Visão Computacional

As imagens podem apoiar estudos de:

1. segmentação do traçado;
2. separação entre sinal, fundo e grade;
3. detecção de linhas e bordas;
4. avaliação da qualidade da imagem;
5. identificação de cortes, inclinação ou desfoque;
6. extração de características visuais;
7. reconhecimento futuro de padrões, desde que existam rótulos clínicos confiáveis.

## Limitações

Os nove identificadores compartilham o identificador-base `1006427285`. Eles representam augmentações relacionadas, e não nove pacientes independentes.

A seleção comprova a organização de 108 imagens, mas possui baixa diversidade clínica.

Em futuros modelos, treino, validação e teste deverão ser separados pelo identificador-base. Isso impede que imagens relacionadas apareçam em conjuntos diferentes e produzam métricas artificialmente elevadas.

Não existem rótulos diagnósticos comprovados nesta seleção. Portanto, as imagens não devem ser classificadas como normais ou associadas a doenças sem evidência adicional.

## Governança

* A licença aparece como Unknown.
* O uso é exclusivamente acadêmico.
* A fonte original permanece identificada.
* Não se deve realizar tentativa de reidentificação.
* Os identificadores são mantidos apenas para rastreabilidade técnica.
* Resultados futuros exigirão validação clínica e supervisão humana.
* Nenhum modelo derivado deverá ser apresentado como diagnóstico autônomo.
