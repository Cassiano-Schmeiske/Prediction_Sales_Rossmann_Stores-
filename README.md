# Prediction Sales Rossmann Stores

<div align="center">
<img src="https://user-images.githubusercontent.com/94291995/161288814-c64d12a3-6158-4b53-b052-a1d41788cabb.png" />
</div>


Este projeto foi desenvolvido durante o curso DS_em_Produção'-By Meigarom Lopes, "ComunidadeDS". Solução para um problema de competição do Kaggle: https://www.kaggle.com/c/rossmann-store-sales

A Rossmann opera mais de 3.000 drogarias em 7 países europeus. Atualmente, os gerentes de loja da Rossmann têm a tarefa de prever suas vendas diárias com até seis semanas de antecedência. As vendas da loja são influenciadas por muitos fatores, incluindo promoções, competição, feriados escolares e estaduais, sazonalidade e localidade. Com milhares de gerentes individuais prevendo vendas com base em suas circunstâncias únicas, a precisão dos resultados pode ser bastante variada. Nesse sentido, o CFO pede a previsão de todas as lojas de forma antecipe a venda em até 6 semanas.



# Project Development Method

The project was developed based on the CRISP-DS (Cross-Industry Standard Process - Data Science, a.k.a. CRISP-DM) project management method, with the following steps:

<img src="https://user-images.githubusercontent.com/94291995/161871338-a03746fb-ff49-4aff-b91b-2a8f3326bbd7.png" alt="health insurance logo" title="Health Insurance" align="right" height="350" class="center"/>


- Business Understanding;
- Data Collection;
- Data Cleaning;
- Exploratory Data Analysis (EDA);
- Data Preparation;
- Machine Learning Modelling and fine-tuning;
- Model and Business performance evaluation / Results;
- Model deployment.


  ## Top Three Data Insigths
  
**H1. Lojas com maior sortimentos deveriam vender mais: True**

|assortment|store|sales|
|---------|------|------------|
|basic	  | 593  |  50.155959 |  
|extended	| 513  |  48.636070 |  
|extra	  | 9	   |   1.207971 |  

![sortimentos](https://user-images.githubusercontent.com/94291995/162541917-b8d7d7d5-e597-4de5-900c-852e53d2683e.png)

**H2. Lojas com competidores mais próximos deveriam vender menos: False**

![COMPETIDORES ](https://user-images.githubusercontent.com/94291995/162542451-ff359aa8-9e61-4983-adf5-665849857188.png)


**H11. Lojas deveriam vender mais depois do dia 10 de cada mês: True**

![after_10_days](https://user-images.githubusercontent.com/94291995/162542998-914b222d-1892-4599-99d4-f9e1b10d7a49.png)

# Machine learning modeling

* Average Model
* Linear Regression Model
* Linear Regression Regularized Model (Lasso)
* Random Forest Regressor
* XGBoost Regressor

 **Cross-validation**
&nbsp; 
  <p align="center">
    <img width="75%" alt="drawing" src="https://user-images.githubusercontent.com/94291995/162535013-061de674-ad83-4a34-825b-2be54587fc22.png">
  </p>
  &nbsp; 
  
 **Compare Model's Performance**
  
|Model|MAE|MAPE|RMSE|
|-----------------------------|-------------------|--------------|------------------|
|Random Forest Regressor 	    |837.7 +/- 219.24 	|0.12 +/- 0.02 |1256.59 +/- 320.28|
|Liner Regression 	          |2081.73 +/- 295.63 |0.3 +/- 0.02  |2952.52 +/- 468.37|
|Lasso 	                      |2116.38 +/- 341.5  |0.29 +/- 0.01 |3057.75 +/- 504.26|
|XGBoost Regressor 	          |7049.23 +/- 588.53 |0.95 +/- 0.0  |7715.24 +/- 689.33|

**Hyperparameter tuning**

|Model|MAE|MAPE|RMSE|
|-----------------------------|-------------------|--------------|------------------|
|XGBoost Regressor 	          |  760.056875 	    |   0.114527 	 |  1088.444636     |

# Business performance

|Store|Predictions|Worst_scenario|best_scemario|MAE|MAPE
|----|----------------|-------------|-------------|---------|---------|
|889 |  	$158,711.33 |	$158,422.78 |	$158,999.87 |	$288.55 |	7.69%   |
|622 |  	$169,909.09 |	$169,608.48 |	$170,209.71 |	$300.62 |	7.21%   |
|558 |  	$123,775.46 |	$123,471.92 |	$124,079.00 |	$303.54 |	9.47%   |
|307 |  	$104,756.21 |	$104,480.17 |	$105,032.25 |	$276.04 |	12.28%  |
|208 |  	$111,051.20 |	$110,779.90 |	$111,322.49 |	$271.30 |	8.51%   |

**Total Performance**
|Scenario|Values|
|-------------------|-------------------|
| 	predictions 	  | R$287,260,416.00  |
| 	worst_scenario 	| R$286,409,667.62  |
| 	best_scenario 	| R$288,111,145.61  |

![Performance](https://user-images.githubusercontent.com/94291995/162547424-a170ccd6-3b04-41ce-a3fb-a523307743fd.png)


# Machine Learning Performance 

![Machine Learning Performance](https://user-images.githubusercontent.com/94291995/162546702-575a085d-ffad-43f9-b055-36df061e0d62.png)

# How to get the prediction

* Send the store number (one each time) and get the sales prediction for the next six weeks.
* If the store number does not exist, it will get as an answer the message: "Store Not Available".


![RossmannBot](https://user-images.githubusercontent.com/94291995/162533744-854eb109-0c71-41f3-8519-4d7dd0cc9d92.gif)

# Deploy Model To Production

 * Back end: Heroku
 * Front end web: Telegram
 * Database: Kaggle

# Conclusion

Considering the first CRISP-DS cycle, the final model presented a usefull performance, considering the MAPE (Mean Absolute Percentage Error) of 0.11. However, for some stores, higher MAPE values were observed, such as 0.37 and 0.52, but this is a point that could be improved in the next CRISP cycle.

# Technologies

* Jupyter notebook
* Python
