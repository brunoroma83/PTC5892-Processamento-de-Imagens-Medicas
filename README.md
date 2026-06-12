# PTC5892-Processamento-de-Imagens-Medicas

# Método Otsu (1979) — Limiarização Global Automática

Este repositório contém uma implementação detalhada, puramente matemática e estatística, do clássico **Método de Otsu**, proposto por Nobuyuki Otsu em 1979. O objetivo principal do algoritmo é realizar a segmentação automática de imagens em escala de cinza, separando-as em duas classes (fundo e objeto) sem a necessidade de intervenção humana.

---

## 📌 Visão Geral do Método

O grande mérito do Método de Otsu é determinar o limiar ideal ($k$) baseado puramente na estatística do histograma da imagem. Ele busca o limiar que divide o histograma de forma que as duas classes (fundo e objeto) fiquem o mais separadas/distintas possível. 

Matematicamente, isto pode ser feito de duas maneiras equivalentes:
1. Minimizando a variância dentro das classes (*within-class variance*).
2. **Maximizando a variância entre as classes (*between-class variance* - $\sigma_B^2$)**, que é o caminho computacionalmente mais eficiente adotado neste projeto.

---

## 🛠️ Conteúdo do Notebook

O projeto está estruturado em etapas sequenciais para demonstrar o funcionamento prático do algoritmo:

1. **Geração da Imagem de Teste:** Criação de uma matriz sintética ($30 \times 30$) em escala de cinza contendo formas geométricas (como um círculo/infinito) para simular o objeto e o fundo.
2. **Análise de Histograma:** Plotagem e cálculo das frequências de distribuição dos níveis de cinza ($L = 256$).
3. **Processamento Estatístico:**
   * Cálculo das probabilidades de ocorrência de cada nível de pixel.
   * Cálculo dos pesos das classes ($\omega_0$ e $\omega_1$).
   * Cálculo das médias acumuladas ($\mu_0$ e $\mu_1$).
4. **Otimização do Limiar ($k$):** Varredura completa para encontrar o ponto de máxima variância entre as classes ($\sigma_B^2$). Se múltiplos valores de $k$ apresentarem a mesma variância máxima, é calculada a média entre eles.
5. **Filtragem e Suavização:** Aplicação opcional de filtros de suavização (como o Gaussiano) para testar o comportamento do algoritmo em imagens ruidosas.
6. **Segmentação Final:** Geração e exibição da imagem binária resultante (preto e branco), destacando o objeto do fundo.

---

## 💻 Tecnologias Utilizadas

O código foi desenvolvido em Python 3 utilizando as seguintes bibliotecas científicas:
* [NumPy](https://numpy.org/) — Para a manipulação de matrizes e cálculos matemáticos eficientes.
* [Pillow (PIL)](https://python-pillow.org/) — Para o tratamento e conversão das estruturas de imagem.
* [Matplotlib](https://matplotlib.org/) — Para visualização dos gráficos, histogramas e renderização das imagens segmentadas.

---

## 📂 Links de Referência

* **Artigo Original (1979):** [A Threshold Selection Method from Gray-Level Histograms](https://drive.google.com/file/d/1dld8ujTxxQF7ZRXFuXfHcYwooug1vWgF/view?usp=drive_link)
* **Explicação Detalhada com IA:** [Documento de Apoio Teórico](https://docs.google.com/document/d/1aZmt5RunWN1Sz2Xf035dHkMGTDRThfMSm7bH71FobO4/edit?usp=drive_link)

---
Desenvolvido como um guia prático de estudo para Processamento Digital de Imagens (PDI).

