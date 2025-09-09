# 🐶🐱 Treinamento de Detecção de Gatos e Cachorros com Darknet + Google Drive

Este projeto tem como objetivo treinar um modelo de detecção de objetos utilizando a arquitetura **YOLOv3** na plataforma **Darknet**, com foco em identificar **gatos** e **cachorros** em imagens reais. O treinamento foi realizado por meio de **transfer learning**, aproveitando pesos pré-treinados e adaptando o modelo para um conjunto personalizado de dados.

## 🚀 Visão Geral

- 🔗 **Integração com Google Drive** para armazenamento e edição dos arquivos de configuração e pesos
- 🖼️ **Dataset personalizado** com imagens anotadas de gatos e cachorros
- 🧠 **Transfer learning** usando `darknet53.conv.74` como base
- ⚙️ Treinamento realizado no ambiente **Google Colab**, com suporte à GPU (quando habilitado)
- 📦 Pesos salvos automaticamente e sincronizados com o Drive

## 📁 Estrutura do Projeto


## 🧪 Etapas do Treinamento

1. **Montagem do ambiente no Colab**
2. **Conexão com o Google Drive**
3. **Edição do arquivo `yolov3.cfg`** para:
   - `classes=2`
   - `filters=21` nas camadas antes de cada `[yolo]`
   - `batch=64`, `subdivisions=32`
   - `max_batches=4000`, `steps=3200,3600`
4. **Importação dos pesos base** (`darknet53.conv.74`)
5. **Execução do treinamento** com salvamento automático dos pesos

## 🧠 Inferência

Após o treinamento, o modelo pode ser testado em imagens reais para verificar a detecção de gatos e cachorros. A inferência gera uma imagem com caixas delimitadoras e nomes das classes detectadas.

```bash
./darknet detector test obj.data yolov3.cfg backup/yolov3_last.weights test_image.jpg -dont_show

📌 Observações
O treinamento foi interrompido manualmente após cerca de 1h30, com pesos salvos para futuras inferências

O projeto pode ser retomado a qualquer momento com os pesos salvos

A estrutura foi pensada para facilitar ajustes e reuso em outros conjuntos de dados
