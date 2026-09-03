# Dataset visual - ECG ROI Segmentation Dataset

## Resumo da entrega

Este diretório contém uma seleção acadêmica de **108 imagens de ECG em formato PNG**, preparada para a Parte 3 - Dados Visuais da Fase 1 do projeto CardioIA.

A seleção supera o mínimo de 100 imagens exigido no enunciado e foi organizada da seguinte forma:

- 9 IDs de amostra da fonte;
- 12 derivações por amostra: `I`, `II`, `III`, `aVR`, `aVL`, `aVF` e `V1` a `V6`;
- 9 imagens por derivação;
- 108 imagens de ECG no total;
- máscaras de segmentação não foram incluídas na contagem.

## Fonte original

- **Nome:** ECG ROI Segmentation Dataset
- **Autor no Kaggle:** Gowri Shankar Penugonda
- **URL permanente:** https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped
- **Versão consultada:** 5
- **Tamanho informado pela fonte:** 20,14 GB
- **Quantidade informada pela fonte:** aproximadamente 186 mil arquivos
- **Data de acesso:** 03/09/2026
- **Licença informada pelo Kaggle:** Unknown

Segundo o Data Card, a base contém imagens recortadas de derivações de ECG e máscaras binárias alinhadas. O conjunto foi derivado do PhysioNet 2025 Challenge e produzido por um pipeline de retificação, extração de derivações, sincronização com sinais 1D e projeção do traçado no plano da imagem.

Por essa razão, a natureza dos dados é descrita neste projeto como **imagens derivadas e processadas pela fonte, não geradas pelo grupo**. Não classificamos as imagens como exames clínicos brutos nem afirmamos que representam pacientes independentes, pois o Data Card acessado não fornece evidência suficiente para essas conclusões.

## Critério de seleção

Foram escolhidos nove IDs de amostra consecutivos do primeiro grupo exibido no explorador de dados do Kaggle. Para cada ID, foram reunidas as 12 derivações disponíveis. Essa abordagem garante cobertura equilibrada das derivações e facilita a rastreabilidade.

Os IDs selecionados foram:

- `1006427285-0001`
- `1006427285-0003`
- `1006427285-0004`
- `1006427285-0005`
- `1006427285-0006`
- `1006427285-0009`
- `1006427285-0010`
- `1006427285-0011`
- `1006427285-0012`

O Data Card descreve o ID da pasta como a combinação de um identificador-base e um identificador de augmentação. Portanto, os nove IDs acima devem ser tratados como **variações/augmentações ligadas ao mesmo identificador-base**, e não como nove pacientes independentes. O conjunto é adequado para comprovar a coleta e preparação das 100+ imagens nesta fase, mas sua representatividade clínica é limitada.

## Estrutura dos arquivos

```text
assets/ecg/
|-- README.md
|-- manifest_ecg_108.csv
|-- preview_ecg.png
|-- RELATORIO_VALIDACAO.md
`-- images/
    |-- ecg_001_1006427285-0001_I.png
    |-- ecg_002_1006427285-0001_II.png
    |-- ...
    `-- ecg_108_1006427285-0012_aVR.png
```

O padrão de nome é:

```text
ecg_NNN_SAMPLEID_DERIVACAO.png
```

## Aplicações futuras em Visão Computacional

As imagens podem apoiar estudos de:

1. **Segmentação do traçado:** separar o sinal de ECG do fundo e da grade.
2. **Detecção de linhas e bordas:** localizar a curva do sinal e medir sua continuidade.
3. **Controle de qualidade:** identificar imagens cortadas, desfocadas, inclinadas ou com artefatos.
4. **Extração de características visuais:** transformar morfologia, amplitude e intervalos aparentes em atributos para modelos posteriores.
5. **Reconhecimento de anomalias:** somente em uma etapa futura e após associação com rótulos clínicos confiáveis e validação médica.

Uma aplicação de negócio possível seria uma triagem técnica de exames: o sistema verificaria automaticamente a qualidade do ECG, priorizaria casos com sinal potencialmente anômalo e encaminharia o resultado para revisão profissional. O modelo atuaria como apoio à decisão, nunca como diagnóstico autônomo.

## Governança, ética e limitações

- A licença da base aparece como **Unknown**; por isso, o uso deve permanecer acadêmico, com atribuição da fonte e sem alegação de direito comercial.
- Não existem rótulos diagnósticos comprovados nesta seleção. Nenhuma imagem deve ser chamada de normal, arritmia, infarto ou outra condição clínica sem evidência adicional.
- Os IDs foram mantidos apenas para rastreabilidade técnica. Não se deve tentar identificar pessoas ou combinar esses IDs com outras bases.
- As imagens possuem dimensões variáveis. Isso é compatível com recortes de diferentes derivações e deve ser tratado no pré-processamento do modelo.
- A derivação II costuma ter faixa temporal mais longa e, portanto, largura maior que as demais.
- Os nove IDs selecionados compartilham o mesmo identificador-base; o conjunto não representa diversidade de pacientes.
- Em futuros experimentos, a divisão entre treino, validação e teste deve ser feita pelo identificador-base, nunca por imagem, para impedir vazamento de dados entre augmentações relacionadas.
- Resultados de IA em saúde precisam de validação clínica, monitoramento de vieses, supervisão humana e avaliação em população externa.

## Integridade e reprodutibilidade

O arquivo `manifest_ecg_108.csv` registra nome, ID técnico, augmentação, derivação, dimensões, tamanho e hash SHA-256 de cada imagem. O hash funciona como uma impressão digital do arquivo e permite verificar alterações ou corrupção.

A seleção foi validada com os seguintes resultados:

- 108 arquivos PNG válidos;
- 108 hashes SHA-256 únicos;
- nenhuma duplicata exata;
- 9 imagens de cada uma das 12 derivações;
- nenhum arquivo vazio.
