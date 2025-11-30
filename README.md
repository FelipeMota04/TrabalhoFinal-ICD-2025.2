Classificação de Exoplanetas: Análise e Modelagem Preditiva 🪐
Este projeto aplica técnicas de Ciência de Dados e Machine Learning para classificar exoplanetas em categorias (como Super-Terras e Gigantes Gasosos) com base em dados observacionais da NASA. O objetivo é desenvolver um classificador robusto capaz de lidar com a complexidade e os dados faltantes típicos da astronomia.

👥 Autores
Projeto desenvolvido para a disciplina de Introdução à Ciência de Dados (ICD - 2025.2).

Antônio Ferreira Oliveira Santos - nUSP: 13863967

Felipe Oliveira Leiras da Mota - nUSP: 14675969

Karine dos Santos Toledo - nUSP: 13671171

📂 Estrutura do Projeto
.
├── .vscode/
│   └── settings.json
├── dataset/
│   └── cleaned_5250.csv         # Dataset processado
├── class_exoplanet.ipynb        # Notebook principal com análise e modelagem
├── data_stract.ipynb            # Notebook auxiliar de extração/tratamento
├── confusion_matrix_knn.png     # Resultados visuais
├── curvas_de_aprendizado_comparacao.png
└── README.md
📊 Sobre os Dados
O dataset utilizado provém do catálogo de exoplanetas da NASA, disponível no Kaggle.

Fonte: NASA Exoplanets

Entradas Principais: Magnitude Estelar, Massa, Raio, Raio Orbital, Período Orbital, Excentricidade.

Target: Tipo do Planeta (Gas Giant, Neptune-like, Super Earth, Terrestrial).

🛠️ Metodologia
O fluxo de trabalho foi dividido em 5 etapas principais:

Pré-processamento e Engenharia de Features:

Normalização de unidades físicas (conversão de todas as medidas para a escala de Júpiter para evitar distorções).

Remoção de colunas irrelevantes e metadados não físicos.

Imputação de Dados (Data Imputation):

Utilização de Random Forest Regressor para prever e preencher valores nulos em variáveis críticas como Massa e Raio, preservando as correlações físicas não-lineares.

Correção de Vazamento: A imputação foi ajustada para ocorrer após a divisão de treino/teste para evitar Data Leakage.

Análise Exploratória (EDA):

Estudo da relação Massa x Raio em escala logarítmica.

Análise de viés de detecção em períodos orbitais.

Matriz de correlação para identificar multicolinearidade.

Modelagem:

Comparação entre Random Forest Classifier (modelo principal) e K-Nearest Neighbors (KNN).

Otimização de hiperparâmetros via GridSearchCV.

Balanceamento de classes para lidar com a escassez de planetas terrestres.

Validação Avançada:

Curvas de Aprendizado: Diagnóstico de overfitting/underfitting.

Bootstrap: Análise de estabilidade e intervalo de confiança da acurácia.

Ablation Study: Teste de cenários (apenas dados físicos vs. apenas orbitais) para validar a importância das features.

🚀 Resultados
O modelo Random Forest demonstrou desempenho superior, alcançando uma acurácia de aproximadamente 97%.

Principais Descobertas: A análise confirmou que Massa e Raio são os preditores dominantes para a classificação. Dados puramente orbitais não são suficientes para determinar a composição planetária.

Robustez: As validações estatísticas indicaram que o modelo é estável e não sofre de overfitting severo.

(Exemplo de visualização de performance)

💻 Como Executar
Certifique-se de ter o Python 3.13+ instalado e as seguintes bibliotecas:

Bash

pip install pandas numpy matplotlib seaborn scikit-learn
Clone este repositório.

Abra o arquivo class_exoplanet.ipynb em seu ambiente Jupyter ou VS Code.

Execute as células sequencialmente para reproduzir a análise e o treinamento dos modelos.

Universidade de São Paulo - 2025
