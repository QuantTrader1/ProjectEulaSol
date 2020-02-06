# ProjectEulaSol
projectEulaSol

import time
t0 = time.time()

import pandas as pd
x,L2,A=[],[],[]
for n in range(1,10000000):
    if isPentagonal(n)==True:
        x.append(n)
       
for j in range(len(x)):
    for k in range(len(x)):
        if j>k:
            xNew = x[j]+x[k]
            if xNew in x:
                theNewX=[xNew,x[j],x[k]]
                L2.append(theNewX)
#For x_i
df1=pd.DataFrame(L2)
df1[3]=abs(df1[2]-df1[1])

for i in df1[3]:
    if isPentagonal(i)==True:
        print(i)


t1 = time.time()
total = t1-t0
total
