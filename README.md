# boot   Tüm Ödevler
Proje Patika Temel Python

#Problem 1:
x =[[1,'a',['cat'],2],[[[3]],'dog'],4,5]
flatten = lambda x: [y for l in x for y in flatten(l)] if type(x) is list else [x]  
flatten(x)

#Problem 2:
a = [1, 2], [3, 4], [5, 6, 7]
b = a[::-1]
reversed_A = [elem[::-1] for elem in b]
print(reversed_A)

#Task1 (17.10.2021)
import numpy as np
import math

a=int(input("Lütfen ikinci dereceden ifadenin katsayısını giriniz:"))
b=int(input("Lütfen birinci dereceden ifadenin katsayısını giriniz:"))
c=int(input("Lütfen denklemdeki sabit sayıyı giriniz:"))

delta = math.pow(b,2)-4*(a*c)
if delta > 0:
    kok1= (-b - math.sqrt(delta))/(2*a)
    kok2= (-b + math.sqrt(delta))/(2*a)
    print("Denklemin birinci kökü: ", kok1)
    print("Denklemin ikinci kökü: ", kok2)
elif delta == 0:
    kok1= (-b - math.sqrt(delta))/(2*a)
    kok2= (-b + math.sqrt(delta))/(2*a)  
    print("Denklem çift kat köke sahiptir ve kökler:", kok1)
else:
    print("Denklemin reel sayılarda kökü bulunmamaktadır.")
    
    
    
    
    
    
import matplotlib.pyplot as plt
import seaborn as sns
dataset2 = pd.read_csv("ev_fiyat_tahmini.csv",sep=';')  #Dosya pd.read komutuyla çağrılır.
dataset2

dataset2.isnull().sum() #Çalışılacak data içinde nan veri var mı kontrolünü sağlamak için
dt_new=dataset2.drop(['oda_sayısı','index'],axis=1) #Çalışılacak data içinde gereksiz sütunlar kaldırılır.
dt_new
x = dt_new.iloc[:,:-1].values #Bağımsız değişkenler x değişkenine atanır.
y = dt_new.iloc[:,-1].values  #Bağımlı değişkenler y değişkenine atanır.
from sklearn.linear_model import LinearRegression
model= LinearRegression()
model.fit(x,y)
print(model.coef_)
print(model.intercept_)
y_predict = model.coef_*x + model.intercept_
plt.title('m^2 - Satış Fiyatı')
plt.xlabel("m^2")
plt.ylabel("Satış Fiyatı")
plt.scatter(x,y,color="blue")
plt.plot( x, y_predict,color = "red")
plt.show()

import statsmodels.api as sm
linearModelStats = sm.OLS(y,x) #ilk değer bağımlı ikinci bağımsız değişken

modelSTATS= linearModelStats.fit()
print("STATS Model Değerleri:", modelSTATS.summary())

Yorumlar
Sklearn kütüphanesiyle problem çözdürüldüğünde:

Grafikte tüm veri setlerini içeren ve optimum noktadan geçen bir doğru çizilerek tahminleme yapılabildiği gözlemlenmiştir. Bazı evlerin gerçekte daha pahalı veya daha ucuz olmasının sebebi problemi tek boyutta incelememizdir. Eğer oda sayısını da bir girdi olarak alsaydık ve multiple linear regression veya polynomial
regression yöntemlerini kullansaydık,tahminimiz daha kuvvetli olabilirdi. Statsmodel kütüphanesiyle problem çözdürüldüğünde: Eğim değerinin sklearn'e göre farklı geldiği gözükmektedir. Kurtosis (Basıklık) değeri 1'den büyüktür bu yüzden istenilen sınırlarda değildir. Skew(Çarpıklık) değeri ise 0'a yakın olduğundan bu değer istenilen aralıktadır.
