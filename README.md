# Trabalho IA — Classificador de Facas

Classificador de imagens de facas usando CNN (Convolutional Neural Network) treinada com PyTorch.

---

## Estrutura do projeto

```
/
├── cnn-api-aulas/
│   ├── server.js
│   ├── package.json
│   ├── requirements.txt
│   └── models_saved/
│       └── model.pth
│
├── frontend/
│   └── index.html
│
└── trabalho_facas.ipynb
```

---

## Classes reconhecidas

- Butterfly
- Karambit
- M9 Bayonet
- Skeleton
- Stiletto
- Talon

---

## Como rodar

### Pré-requisitos

- [Node.js](https://nodejs.org/) instalado
- [Python](https://www.python.org/) instalado

---

### 1. Instalar dependências Node.js

```bash
cd cnn-api-aulas
npm install
```

---

### 2. Instalar dependências Python

```bash
pip install torch torchvision pillow
```

---

### 3. Subir a API

```bash
npm start
```

Aguarde a mensagem:

```
API iniciada com modelo carregado.
Servidor rodando em: http://localhost:3000
```

---

### 4. Abrir o frontend

Abra o arquivo `frontend/index.html` diretamente no navegador (clique duplo).

---

### 5. Classificar uma imagem

1. Arraste uma imagem de faca ou clique para selecionar
2. Clique em **Classificar**
3. Veja a classe prevista e a confiança do modelo

---

## Endpoint da API

```
POST http://localhost:3000/infer
```

Campo esperado: `image` (multipart/form-data)

Resposta:

```json
{
  "ok": true,
  "predictedClass": "karambit",
  "predictedIndex": 1,
  "confidence": 0.91,
  "topPredictions": [
    { "class": "karambit",  "index": 1, "confidence": 0.91 },
    { "class": "stiletto",  "index": 4, "confidence": 0.06 },
    { "class": "butterfly", "index": 0, "confidence": 0.03 }
  ]
}
```
