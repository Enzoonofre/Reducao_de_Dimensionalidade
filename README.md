# Conversão de Imagem para Tons de Cinza e Binário

Este projeto utiliza a biblioteca OpenCV para converter uma imagem colorida em tons de cinza normalizados e, posteriormente, em uma imagem binarizada.

## 🚀 Funcionalidades
- Carregamento de uma imagem em cores
- Conversão para escala de cinza normalizada
- Binarização da imagem com limiar
- Exibição dos resultados com Matplotlib

## 🛠 Tecnologias Utilizadas
- **Python**
- **OpenCV**
- **Matplotlib** (para visualização)

## 📜 Instalação

1. Clone este repositório:
   ```bash
   git clone https://github.com/Enzoonofre/Reducao_de_Dimensionalidade.git
   ```
2. Acesse a pasta do projeto:
   ```bash
   cd Reducao_de_Dimensionalidade
   ```
3. Instale as dependências:
   ```bash
   pip install opencv-python matplotlib
   ```

## 📌 Como Executar

1. Certifique-se de ter uma imagem na mesma pasta do script (ex: `lena.jpg`).
2. Execute o script Python:
   ```bash
   python reducao_de_dimensinalidade.py
   ```

## 🖼 Exemplo de Código

```python
import cv2
import matplotlib.pyplot as plt

# Carregar imagem
original = cv2.imread('imagem.jpg')

# Converter para tons de cinza
gray = cv2.cvtColor(original, cv2.COLOR_BGR2GRAY)

# Normalizar a imagem para o intervalo 0-255
gray_normalized = cv2.normalize(gray, None, 0, 255, cv2.NORM_MINMAX, dtype=cv2.CV_8U)

# Converter para binário
_, binary_img = cv2.threshold(gray_normalized, 127, 255, cv2.THRESH_BINARY)

# Exibir resultados
plt.figure(figsize=(12, 6))

plt.subplot(1, 3, 1)
plt.imshow(original[..., ::-1])  # Converter BGR para RGB para exibição correta
plt.axis('off')
plt.title('Original')

plt.subplot(1, 3, 2)
plt.imshow(gray_normalized, cmap='gray')
plt.axis('off')
plt.title('Tons de Cinza')

plt.subplot(1, 3, 3)
plt.imshow(binary_img, cmap='gray')
plt.axis('off')
plt.title('Binária')

plt.show()
```

## 📷 Resultado Esperado
O script gera uma visualização contendo:
1. **Imagem original**
2. **Imagem convertida para tons de cinza normalizados**
3. **Imagem binarizada com limiar de 127**

## 📝 Licença
Este projeto está sob a licença MIT. Sinta-se à vontade para utilizá-lo e modificá-lo. 😃

