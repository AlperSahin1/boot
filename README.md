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
