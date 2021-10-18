# boot
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
