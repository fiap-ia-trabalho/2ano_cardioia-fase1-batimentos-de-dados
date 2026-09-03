# Relatório de validação - seleção visual CardioIA

**Data da validação:** 03/09/2026  
**Fonte:** ECG ROI Segmentation Dataset - Kaggle  
**Seleção:** 108 imagens PNG

## Resultado

| Verificação | Resultado | Status |
|---|---:|:---:|
| Quantidade total de PNGs | 108 | Aprovado |
| Mínimo exigido no enunciado | 100 | Aprovado |
| Arquivos vazios | 0 | Aprovado |
| PNGs inválidos | 0 | Aprovado |
| Hashes SHA-256 únicos | 108 | Aprovado |
| Duplicatas exatas | 0 | Aprovado |
| Derivações representadas | 12 | Aprovado |
| Imagens por derivação | 9 | Aprovado |

## Distribuição por derivação

| Derivação | Quantidade |
|---|---:|
| I | 9 |
| II | 9 |
| III | 9 |
| aVR | 9 |
| aVL | 9 |
| aVF | 9 |
| V1 | 9 |
| V2 | 9 |
| V3 | 9 |
| V4 | 9 |
| V5 | 9 |
| V6 | 9 |

## Ressalva de representatividade

Os nove IDs selecionados compartilham o identificador-base `1006427285` e diferem pelo sufixo de augmentação. Assim, a seleção comprova a preparação de 108 imagens e oferece cobertura equilibrada das derivações, mas não equivale a 108 pacientes ou a nove pacientes independentes.

Para futuros modelos, recomenda-se ampliar o conjunto com diferentes identificadores-base e separar treino, validação e teste pelo identificador-base, evitando vazamento entre augmentações relacionadas.

