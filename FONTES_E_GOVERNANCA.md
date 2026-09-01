# Fontes, rastreabilidade e governança

Este arquivo registra a procedência das três bases utilizadas na Fase 1 do CardioIA.

## 1. Dados numéricos

- **Fonte oficial:** Kaggle — Cardiovascular Disease dataset, por Svetlana Ulianova
- **URL:** https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
- **Natureza:** dados de pacientes coletados no momento de exame médico; portanto, tratados neste projeto como **dados reais**, não sintéticos.
- **Tamanho da fonte:** 70.000 registros, 11 atributos de entrada + variável-alvo.
- **Licença exibida no Kaggle:** **Unknown**.
- **Uso local:** amostra de 100 registros para cumprir o mínimo da atividade, acompanhada de versão preparada e dicionário.
- **Rastreabilidade técnica da amostra:** os 100 registros locais foram conferidos por meio de um espelho público do `cardio_train.csv` associado ao mesmo dataset. Para máxima rastreabilidade, o grupo deve comparar ou substituir a amostra pelo download direto do Kaggle antes da entrega.
- **Risco de qualidade:** estudos que reutilizam a base relatam valores extremos e entradas fisiologicamente improváveis em pressão arterial. Por isso, etapas futuras devem incluir validação de faixas, duplicatas e outliers antes do treinamento.

## 2. Textos médicos

### Diretrizes Brasileiras de Hipertensão Arterial – 2020
- Fonte: SciELO / Arquivos Brasileiros de Cardiologia
- URL: https://www.scielo.br/j/abc/a/Z6m5gGNQCvrW3WLV7csqbqh/?lang=pt
- DOI: 10.36660/abc.20201238
- Licença: Creative Commons Attribution (CC BY), conforme SciELO.

### Diretriz de Síndrome Coronariana Crônica – 2025
- Fonte: SciELO / Arquivos Brasileiros de Cardiologia
- URL: https://www.scielo.br/j/abc/a/GKTmBKCfKXHmSdYCnyJv9PC/?format=html&lang=pt&ilang=en
- DOI: 10.36660/abc.20250619
- Licença: Creative Commons Attribution (CC BY), conforme SciELO.

Os arquivos `.txt` locais são corpora resumidos e parafraseados para uso acadêmico em NLP. O conteúdo integral deve ser consultado nos links oficiais.

## 3. Imagens

- **Fonte:** Kaggle — ECG ROI Segmentation Dataset
- **URL:** https://www.kaggle.com/datasets/gowrishankarp/ecg-dataset-cropped
- **Governança pendente:** confirmar quantidade de imagens, origem real/sintética, licença, classes e presença de dados identificáveis diretamente no Data Card antes da submissão definitiva.

## Princípios de governança adotados

- Rastreabilidade da origem e data de acesso das fontes.
- Separação clara entre dados originais e campos derivados/preparados.
- Não utilização clínica dos dados ou resultados desta atividade.
- Avaliação de qualidade, outliers, balanceamento e viés antes de modelagem.
- Respeito aos termos de uso e licenças de cada fonte externa.
- Verificação de anonimização e de possíveis identificadores em imagens médicas.
