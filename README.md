# 🧠 Classificação e Detecção Multimodal com COCO

Este projeto implementa modelos para **classificação** e **detecção de objetos** utilizando dados multimodais (imagens e legendas) do dataset [COCO](https://cocodataset.org/). Ele explora duas abordagens complementares:

1. **Classificação Multimodal**: combina imagens e legendas usando modelos de deep learning.
2. **Detecção de Objetos**: aplica o modelo **Faster R-CNN** para localizar e identificar objetos nas imagens.

## 📁 Estrutura do Projeto

```
├── models/               # Modelos treinados
├── results/              # Resultados quantitativos e qualitativos
└── README.md             # Este arquivo
```

## 🎯 Objetivos

- Treinar um modelo de **classificação multimodal** com representações visuais e textuais.
- Treinar e avaliar um modelo de **detecção de objetos** baseado em **Faster R-CNN** com métricas como mAP.
- Testar visualmente previsões em imagens reais do COCO.

## 🗂️ Dataset

- **COCO 2017**:
  - 3k imagens para treino (de ~118k imagens totais)
  - 3 categorias: person, dogs e cars
  - 5 legendas por imagem
  - Anotações detalhadas de objetos com bounding boxes
- Link: https://cocodataset.org/#download

## 🔧 Pré-processamento

- **Imagens**: redimensionamento e normalização.
- **Legendas**: tokenização com modelos como BERT ou CLIP.
- **Detecção**: parsing das anotações COCO (bounding boxes e classes).

## 🧠 Modelos

### Classificação Multimodal

- **Imagem**: ResNet, ViT, CLIP-Vision
- **Texto**: BERT, CLIP-Text
- **Fusão**: concatenação ou atenção cruzada
- **Saída**: classes via softmax ou sigmoid

### Detecção de Objetos

- **Modelo**: [Faster R-CNN](https://arxiv.org/abs/1506.01497)
- **Framework**: PyTorch (torchvision)
- **Métricas**: mAP@0.5, mAP@0.5:0.95

### Notebook Principal

1. Instalação de dependências
2. Configuração dos caminhos e hiperparâmetros
3. Definição da classe `COCODataset`
4. Transformações e augmentations
5. Criação do modelo Faster R-CNN
6. Loop de treinamento e validação
7. Avaliação com mAP
8. Visualização de previsões

## 📈 Avaliação

- Classificação:
  - Acurácia, Precision, Recall, F1-score
- Detecção:
  - mAP@IoU=0.5
  - mAP@[.5:.95] (intervalo de IoUs)
- Visualização: bounding boxes desenhados nas imagens com rótulos e scores

## 🚀 Como Rodar

1. Clone o repositório:

```bash
git clone https://github.com/vini-mon/COCO_Class-Redes_Neurais
cd COCO_Class-Redes_Neurais
```

2. Baixe os dados COCO (treino e validação)

3. Execute os scripts ou notebooks:

- **Classificação multimodal**: `python notebook.py`

## 💡 Aplicações

- Sistemas autônomos de reconhecimento de cenas
- Análise de conteúdo multimodal

## 🧪 Tecnologias

- Python 3
- PyTorch, torchvision
- Transformers (HuggingFace)
- OpenCV, matplotlib
- COCO API