# Clustering - Tópicos em IA

Análise comparativa de algoritmos de clustering em diferentes estruturas de dados. Este projeto implementa e avalia **K-Means**, **DBSCAN** e **Clusterização Hierárquica** utilizando datasets desafiadores da scikit-learn.

## Sobre o Projeto

Este trabalho é uma análise aprofundada de algoritmos de clustering, com foco em compreender como diferentes métodos se comportam diante de estruturas de dados variadas. O projeto demonstra que a escolha do algoritmo deve estar alinhada à geometria e distribuição dos dados.

## Objetivos

- Comparar o desempenho de três algoritmos de clustering
- Analisar comportamento em diferentes estruturas de dados
- Avaliar métricas de coesão e separabilidade
- Investigar impacto de hiperparâmetros
- Demonstrar a importância da escolha correta do algoritmo

## Datasets Utilizados

### 1. **make_moons**
Dois semicírculos intercalados que formam uma estrutura não linearmente separável. Desafia algoritmos baseados em centroides.

### 2. **make_blobs**
Três agrupamentos esféricos bem definidos e separados. Cenário ideal para K-Means e DBSCAN com parâmetros bem ajustados.

### 3. **make_circles**
Dois círculos concêntricos (anéis). Estrutura altamente não linear que requer métodos sofisticados para capturar a geometria corretamente.

## Algoritmos Implementados

### K-Means
- **Melhor desempenho:** make_blobs (ARI: 1.0, Silhouette: 0.81)
- **Limitações:** Falha em estruturas não lineares (circles e moons)
- **Características:** Rápido, mas assume clusters convexos

### DBSCAN
- **Melhor desempenho:** make_blobs com eps=0.3 (ARI: 1.0, Silhouette: 0.81)
- **Vantagens:** Detecta estruturas arbitrárias, identifica outliers
- **Desvantagem:** Sensível aos parâmetros eps e min_samples

### Clusterização Hierárquica
- **Melhor desempenho:** make_blobs com qualquer linkage (ARI: 1.0)
- **Flexibilidade:** Comportamento varia conforme método de ligação (linkage)
- **Interpretabilidade:** Dendrograma fornece visão hierárquica dos agrupamentos

## Métricas de Avaliação

- **Adjusted Rand Index (ARI)** [-1, 1]: Mede correspondência com labels verdadeiros (1 = perfeito)
- **Silhouette Score**: Avalia coesão interna e separação entre clusters
- **Normalized Mutual Information (NMI)** [0, 1]: Informação compartilhada entre clusters e classes
- **V-measure** [0, 1]: Média harmônica entre homogeneidade e completude

## Como Usar

### Requisitos
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

### Usar o Colab
Acesse o notebook interativo: [Google Colab](https://colab.research.google.com/drive/1rg6qPFpwyH_LNrsP3mjuy9lLcE7u5Klu?usp=sharing)
