# boot
Proje Patika Temel Python
x =[[1,'a',['cat'],2],[[[3]],'dog'],4,5]
flatten = lambda x: [y for l in x for y in flatten(l)] if type(x) is list else [x]  
flatten(x)
