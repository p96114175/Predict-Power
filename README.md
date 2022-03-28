# 預測台電電力 P96114175
NCKU DSAI HW1 - Electricity Forecasting

應用台電2021、2022年所提供的電力資訊包，針對我們Linear regression 線性回歸模型進行訓練，最後對2022/03/30 ~ 2022/04/13做出備轉容量(MW)的預測。

# Data Preprocess
首先針對 Dataset 的關聯性進行分析，可以得知 Dataset 中 'rate'、'people_use'、'ele_pro'、'sun'和備轉容量(MW)的關聯性較高，接著根據上述類項，將差異大的資料進行刪除離群值處理，以便於後續得到的RMSE較為準確

![image](https://user-images.githubusercontent.com/102530486/160413929-10e91b37-1cf2-4621-b179-247baf70cebd.png)
# Model Intro
預測電力時使用的模型為線性回歸（Linear regression）。當只有一個自變數和一個依變數的情形稱為簡單線性回歸(Simple linear regression)，大於一個自變數的情形稱為多元回歸(multiple regression)。
# Model training
將 Data Preprocess後的Dataset進行資料集建置，再把預訓練的資料值做特徵縮放(StandardScaler)，最後放入模型訓練
# Model Verify
RMSE(Root Mean Square Error)為最常用的回歸損失函數，計算方法是求預測值與真實值之間距離的平方和接著開根號，對模型進行評估，若 RMSE 的值越小，說明預測模型描述實驗資料具有更好的精確度。
![image](https://user-images.githubusercontent.com/102530486/160423194-031ceb13-b7f1-46c0-b642-f44377172513.png)

# Run the code
環境 Python 3.7.1

輸入以下指令

```
python3 -m pip install -r requirements.txt
```
	python predict_power.py --training train.csv --output submisson.csv
