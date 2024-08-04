# Health-Data-Project

Este repositório contém o projeto de Análise Exploratória de Dados (EDA) realizado com uma base de dados de saúde. O objetivo principal deste projeto é explorar e analisar os dados para extrair insights que possam ser úteis para entender melhor os padrões e tendências relacionadas à saúde.

## Descrição dos Arquivos

- `Projeto_HealthData.ipynb`: Notebook principal contendo todo o processo de análise e modelagem.
- `data/`: Diretório contendo os dados utilizados no projeto.
- `models/`: Diretório para salvar os modelos treinados.
- `results/`: Diretório para salvar os resultados e visualizações geradas.

## Base de dados
- Record ID
   - RecordID: A unique identifier assigned to each record (1 to 2392).

- Air Quality Metrics
   - AQI: Air Quality Index, a measure of how polluted the air currently is or how polluted it is forecast to become.
   - PM10: Concentration of particulate matter less than 10 micrometers in diameter (μg/m³).
   - PM2_5: Concentration of particulate matter less than 2.5 micrometers in diameter (μg/m³).
   - NO2: Concentration of nitrogen dioxide (ppb).
   - SO2: Concentration of sulfur dioxide (ppb).
   - O3: Concentration of ozone (ppb).

- Weather Conditions
   - Temperature: Temperature in degrees Celsius (°C).
   - Humidity: Humidity percentage (%).
   - WindSpeed: Wind speed in meters per second (m/s).

- Health Impact Metrics
   - RespiratoryCases: Number of respiratory cases reported.
   - CardiovascularCases: Number of cardiovascular cases reported.
   - HospitalAdmissions: Number of hospital admissions reported.
   
- Target Variable: Health Impact Class
   - HealthImpactScore: A score indicating the overall health impact based on air quality and other related factors, ranging from 0 to 100.
   - HealthImpactClass: Classification of the health impact based on the health impact score:
      0: 'Very High' (HealthImpactScore >= 80)
      1: 'High' (60 <= HealthImpactScore < 80)
      2: 'Moderate' (40 <= HealthImpactScore < 60)
      3: 'Low' (20 <= HealthImpactScore < 40)
      4: 'Very Low' (HealthImpactScore < 20)

## Objetivos

Os principais objetivos deste projeto são:

- Realizar uma análise descritiva dos dados.
- Identificar padrões, tendências e correlações nos dados.
- Gerar visualizações para comunicar insights relevantes.

## Metodologia

1. **Preparação dos Dados**:
   - Carregamento da base de dados.
   - Tratamento de dados ausentes e/ou inconsistentes.

2. **Análise Exploratória de Dados**:
   - Estatísticas descritivas.
   - Visualizações (gráficos de barras, histogramas, boxplots, etc.).
   - Análise de correlações entre variáveis.

3. **Interpretação dos Resultados**:
   - Discussão sobre os principais achados.
   - Insights relevantes para a área de saúde baseados nos dados analisados.

## Principais Conclusões

### Análise Exploratória de Dados (EDA)
- Identificamos que a coluna "HealthImpactScore" está diretamente relacionada com a coluna do target, portanto, foi desconsiderada nas análises subsequentes.
- A coluna "AQI" (Índice de Qualidade do Ar) foi identificada como a mais correlacionada com o target, indicando sua importância na previsão do impacto na saúde.

### Modelos Treinados
- Treinamos e avaliamos vários modelos, incluindo Random Forest, SVC, KNN e Decision Tree.
- O modelo Random Forest apresentou o melhor desempenho geral, com uma acurácia de 0.96.

### Ajuste de Hiperparâmetros
- Utilizamos `GridSearchCV` para ajustar os hiperparâmetros do modelo Random Forest, resultando em uma melhoria no desempenho geral.
- Os melhores hiperparâmetros encontrados foram: `bootstrap=False`, `max_depth=30`, `min_samples_leaf=1`, `min_samples_split=5`, `n_estimators=300`.

### Desempenho do Modelo
- O modelo ajustado apresentou alta precisão e recall para a maioria das classes, exceto para as classes "Low" e "Very Low", que ainda apresentaram desafios.
- Aplicamos técnicas de balanceamento de classes, como SMOTE, para tentar melhorar o desempenho nas classes minoritárias.

### Visualização
- Plotamos a matriz de confusão para visualizar o desempenho do modelo Random Forest ajustado, destacando as áreas onde o modelo teve dificuldades.

## Próximos Passos

Para futuras melhorias, consideramos as seguintes abordagens:
- **Balanceamento de Classes**: Continuar explorando técnicas de balanceamento de classes para melhorar o desempenho nas classes "Low" e "Very Low".
- **Ajuste de Pesos**: Ajustar os pesos das classes no modelo para dar mais importância às classes minoritárias.
- **Ensemble de Modelos**: Combinar diferentes modelos para melhorar a robustez e o desempenho geral.

## Conclusão Final

O projeto demonstrou a eficácia do modelo Random Forest na previsão do impacto na saúde com base em dados de qualidade do ar. No entanto, há espaço para melhorias, especialmente nas classes minoritárias. Continuar explorando e ajustando os modelos pode levar a previsões ainda mais precisas e úteis para a tomada de decisões em saúde pública.

Este notebook forneceu uma visão abrangente do processo de modelagem preditiva, desde a análise exploratória de dados até o ajuste de hiperparâmetros e avaliação de modelos. Esperamos que as técnicas e insights apresentados aqui sejam úteis para futuros projetos de análise de dados e aprendizado de máquina.

## Ferramentas Utilizadas

- Python
- Bibliotecas principais: Pandas, Matplotlib, Seaborn, Scikit-learn, entre outras.

## Como Executar

Para reproduzir a análise realizada neste projeto, siga estes passos:

1. Clone este repositório para o seu ambiente local:
   ```git clone https://github.com/Mariana-Marinho/Health-Data-Project```
2. Navegue até o diretório do projeto:
   ```cd Health-Data-Project```
3. Crie um ambiente vitual:
   ```python -m venv venv```
4. Ative o ambiente virtual:
   - No Windows:
      ```venv\Scripts\activate```
   - No macOS/Linux:
      ```source venv/bin/activate```
5. Instale as dependências:
   ```pip install -r requirements.txt```
6. Execute o notebook:
   ```jupyter notebook Projeto_HealthData.ipynb```

## Contribuições
Contribuições são bem-vindas. Sinta-se à vontade para enviar pull requests com melhorias ou correções neste projeto.

## Autor

[Mariana Marinho](https://github.com/Mariana-Marinho) <br>
[Laís Amorim](https://github.com/laisorim5)

## Licença
Este projeto está licenciado sob a Licença MIT.
