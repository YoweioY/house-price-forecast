# -預測房價(利用圖片與數值輸入神經網路模型預測房價)
一、前言

4項數值:房間數量、浴室數量、房屋面積、郵遞區號；4種照片:房間照片、浴室照片、廚房照片、房屋正面照片；

利用以上8項作為input，預測房價(數值)。

二、資料

訓練集如Train.csv，測試集如Test.csv，
資料為字串，進行分割後數值按順序分別為房間數、廁所數、面積、郵遞區號、房價、廁所照片檔名、房間照片檔名、房屋照片檔名、廚房照片檔名。

訓練集圖片:https://reurl.cc/qrOKVy 
測試集圖片:https://reurl.cc/xLOK6V 

三、方法

1.數值前處理: 經過EDA，將郵遞區號刪除並做偏態處理與標準化，並將數值轉換為圖片格式大小(如:數值3->256x256x1，相當於256x256個都是3的數值)
2.圖片前處理: 將圖片統一為256x256的大小並做標準化
3.將數值與圖片合併成(256,256,15)的大小
4.input進model中，圖片的部份先做resnet處理並output，再將output結果與數值合併進神經網路做最後的預測。

四、結果

從下圖可看出loss有明顯下降，在loss不再下降後停止訓練，並輸出模型。
模型:https://reurl.cc/E4pbVK 

![image](https://github.com/YoweioY/house-price-forecast/assets/91478099/41b97913-dc72-47b5-8d1a-53c1d15394e2)

將預測值與測試集資料做比對可發現模型雖無法準確預測實際值但可大略預測房價變化之趨勢，MAE=3202100.98，RMSE=4153473.84，R^2=36%
![image](https://github.com/YoweioY/house-price-forecast/assets/91478099/3450c13d-01fc-4506-8fe2-d2a7a508ef76)





