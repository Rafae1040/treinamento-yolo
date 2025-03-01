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



## 🎯 **Conclusão e Possíveis Melhorias**

### **🔎 Resumo da Solução**
Este projeto demonstra como utilizar o YOLOv8 no Google Colab para detecção de objetos em imagens sem precisar de uma GPU. Utilizamos um modelo pré-treinado para simplificar a inferência, tornando o processo acessível a qualquer usuário.

### **🔍 Buscando Alternativas para Rodar o Projeto**
Inicialmente, tive dificuldades para rodar a detecção de objetos devido a limitações de hardware, como a ausência de uma GPU potente. Para contornar esse problema, explorei algumas alternativas:
1. **Google Colab**: Utilize o poder da nuvem para rodar o YOLOv8 sem precisar de uma máquina robusta.
2. **Uso de Transfer Learning**: Em vez de treinar um modelo do zero, aproveitei um modelo pré-treinado para acelerar o processo e evitar uso excessivo de recursos.
3. **Ajuste do Modelo**: Optei pelo YOLOv8n (nano), uma versão mais leve que pode rodar mesmo sem GPU dedicada.

Essas estratégias permitiram que eu conseguisse executar o projeto mesmo com limitações de hardware. 💡

## Possibilidades de Resolução de Negócios

### **1️⃣  Gestão de Estoque Automatizada**
Contagem automática de produtos: Utilização de câmeras e modelos YOLO para contar itens em prateleiras ou esteiras transportadoras, eliminando erros humanos e atualizando o estoque em tempo real.

Detecção de discrepâncias: Identificação de itens faltantes, em excesso ou fora do lugar, com alertas automáticos para correções.

Otimização de espaço: Análise da disposição de produtos para maximizar o uso do armazém e reduzir custos com espaço.

### **2️⃣ Rastreabilidade em Tempo Real**
Identificação de produtos: Uso de códigos de barras, QR codes ou reconhecimento visual para rastrear produtos em todas as etapas do processo logístico.

Monitoramento de movimentações: Rastreamento de paletes, caixas e veículos dentro do armazém, com registro automático de entradas, saídas e transferências.

Histórico completo: Geração de relatórios detalhados sobre o caminho percorrido por cada produto, desde o recebimento até a expedição.

### **3️⃣ Detecção de Problemas e Segurança**
Inspeção de qualidade: Identificação automática de produtos danificados ou embalagens comprometidas durante o transporte ou armazenamento.

Monitoramento de segurança: Detecção de situações de risco, como empilhamento inadequado de paletes ou obstruções em corredores.

Acesso controlado: Uso de câmeras para monitorar áreas restritas e evitar acessos não autorizados.

### **4️⃣ Integração com Sistemas Existentes**
Conectividade com WMS/ERP: Integração dos dados de visão computacional com sistemas de gestão de armazéns (WMS) ou planejamento de recursos empresariais (ERP) para decisões mais ágeis e precisas.

Dashboards intuitivos: Visualização de métricas como níveis de estoque, eficiência operacional e alertas em tempo real.



