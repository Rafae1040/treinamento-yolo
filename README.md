# 🎯 Detecção de Objetos com YOLO

Este projeto demonstra como utilizar o modelo **YOLOv8** para detecção de objetos no Google Colab, sem necessidade de GPU. Utilizamos a biblioteca **Ultralytics**, que simplifica o uso do YOLO, permitindo tanto inferência (detecção de objetos) quanto o treinamento de novos modelos.

## 📌 **Requisitos**
- ✅ Conta no **Google Colab**
- 🌐 Conexão com a internet
- 🛠 Biblioteca **Ultralytics** instalada

## 🚀 **Passo a Passo**

### **1️⃣ Instalar Dependências**
Antes de tudo, instale a biblioteca **YOLOv8**:


```python
!pip install ultralytics
```
📦 Isso instalará todas as dependências necessárias para rodar o modelo YOLOv8 no Google Colab.

### **2️⃣ Importar as Bibliotecas**
Para trabalhar com detecção de objetos, importamos as bibliotecas principais:
```python
from ultralytics import YOLO
from google.colab.patches import cv2_imshow  # Para exibir imagens no Colab
import cv2
```

### **3️⃣ Carregar o Modelo YOLOv8**
🖥️ O YOLOv8 possui diversas versões, desde modelos pequenos (rápidos e leves) até modelos grandes (mais precisos, mas pesados). Neste projeto, utilizamos a versão **YOLOv8n** (nano), que é otimizada para CPU.
```python
# Carregar o modelo YOLOv8n (versão pequena para CPU)
model = YOLO("yolov8n.pt")
```

### **4️⃣ Fazer a Detecção em uma Imagem**

📷 Podemos testar a detecção em qualquer imagem, seja uma local ou uma hospedada na internet:
```python
# Fazer a detecção em uma imagem de teste
results = model("https://ultralytics.com/images/zidane.jpg")  # URL de imagem

# Exibir a imagem com os resultados
results[0].show()
```

🔍 O YOLOv8 retorna os objetos detectados na imagem, desenhando caixas delimitadoras (**bounding boxes**) ao redor de cada objeto identificado.

### **5️⃣ Salvar a Imagem Processada**
💾 Depois da detecção, podemos salvar a imagem com os resultados:

#### 🔹 **Salvar localmente no Colab**
```python
results[0].save(filename="resultado.jpg")
```

📁 A imagem será salva na pasta principal do Colab (`/content/resultado.jpg`).

#### 🔹 **Baixar a imagem para o seu computador**
Caso queira baixar a imagem diretamente para o seu dispositivo:
```python
from google.colab import files
files.download("resultado.jpg")
```

#### 🔹 **Salvar no Google Drive**
Se preferir salvar a imagem no **Google Drive**, conecte sua conta e especifique o caminho:
```python
from google.colab import drive
drive.mount('/content/drive')  # Conectar ao Google Drive

# Salvar no Google Drive
results[0].save(filename="/content/drive/MyDrive/resultado.jpg")
```
🗂️ Agora, a imagem estará acessível na pasta **Meu Drive**.

---

## 🎯 **Conclusão e Possíveis Melhorias**

### **🔎 Resumo da Solução**
Este projeto demonstra como utilizar o YOLOv8 no Google Colab para detecção de objetos em imagens sem precisar de uma GPU. Utilizamos um modelo pré-treinado para simplificar a inferência, tornando o processo acessível a qualquer usuário.

### **🔍 Buscando Alternativas para Rodar o Projeto**
Inicialmente, tive dificuldades para rodar a detecção de objetos devido a limitações de hardware, como a ausência de uma GPU potente. Para contornar esse problema, explorei algumas alternativas:
1. **Google Colab**: Utilize o poder da nuvem para rodar o YOLOv8 sem precisar de uma máquina robusta.
2. **Uso de Transfer Learning**: Em vez de treinar um modelo do zero, aproveitei um modelo pré-treinado para acelerar o processo e evitar uso excessivo de recursos.
3. **Ajuste do Modelo**: Optei pelo YOLOv8n (nano), uma versão mais leve que pode rodar mesmo sem GPU dedicada.

Essas estratégias permitiram que eu conseguisse executar o projeto mesmo com limitações de hardware. 💡



