# Dataset numérico — CardioIA

Esta pasta contém a base numérica preparada para a Parte 1 da Fase 1 do CardioIA.

## Fonte

* **Dataset:** Cardiovascular Disease Dataset
* **Autora:** Svetlana Ulianova
* **Plataforma:** Kaggle
* **URL:** https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
* **Natureza:** dados reais, não sintéticos, segundo a descrição da fonte
* **Licença apresentada:** Unknown

## Arquivos

* `cardio_train_amostra_100.csv`: 100 registros preservando a estrutura original.
* `cardio_train_amostra_100_preparada.csv`: versão tratada e com nomes legíveis.
* `cardio_train_amostra_100_preparada.xlsx`: versão compatível com Excel.
* `dicionario_dados.csv`: descrição das variáveis.

## Transformações

Na versão preparada foram realizadas:

* conversão da idade de dias para anos;
* cálculo do IMC;
* tradução dos nomes das colunas;
* padronização das categorias;
* preservação do identificador original;
* manutenção da variável-alvo cardiovascular.

## Possíveis aplicações

* classificação de risco;
* análise exploratória;
* clusterização de perfis;
* detecção de outliers;
* avaliação de importância das variáveis;
* apoio futuro à triagem.

## Cuidados

Antes do treinamento de um modelo, devem ser verificadas faixas fisiológicas, duplicidades, valores ausentes, equilíbrio da variável-alvo e possíveis vieses demográficos.

A base possui finalidade acadêmica e não deve ser utilizada para diagnóstico.
