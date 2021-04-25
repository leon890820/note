# Apriori 穴道與病名的關聯性分析

## 0. Abstract

This study was conducted based on Apriori algorithm-based association rule analysis. We use python to calculate the association with acupoints and disease. We find top 23 frequence acupoints were  `Extra12`, `TF4`, `LI4`, `LI11`, `ST25`, `ST36`, `ST44`, `CO4`, `CO18`, `CO1`, `HX1`, `CO17`, `HT7`, `SP6`, `GB28`, `RN12`, `RN9`, `RN4`, `CO13`, `REN12`, `REN9`, `REN4`, `LR3` .We investigated 3960 association rule. Analisis by Apriori, the result that  {Extra12} and {TF4} are most relantive to this form.(Table.1).`LI4,ST36->ST44` , `LI4,ST44->ST36` ,`ST36,ST44->LI4` were the most associated rule in the datas.(Fig.4)

Recently, data mining methods have been widely used in acupuncture and Chinese medicine[1]. Apriori is a method to find each data's association. It identify the frequence for every item in database and find association to other objects. Then we can know which items are most relatived. 

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_eb0fb5ded73d1a08cb3f93a6a4fe8122.png)
Table.1 the data of acupoints


## 2. Materials and Methods
2.3. Data Analysis. 

In this case, we get the data by a doctor. The form of data can see in Table.1. We extracted and analyzed the frequency of the acupoints. In this study, the Apriori algorithm-based association rule analysis and plotting were processed using software python. By using Apriori, we can find someing that hidden rules. We use conditional probability to calculate each acupoint's support. Mathematically, support is the fraction of the total number of transactions in which the item set occurs. And we delete acupoints that support is less than 30%.

$$
support(A)={P(A)}=\frac{times}{all}
$$

Next, we calculate next layer based on last. We conbine the acupoints that didn't be delete and calculate support, confidence and lift.

$$
confidence(A \rightarrow B)=P(B|A)=\frac{P(A \cap B)}{P(A)}\\
lift(A \rightarrow B)=\frac{confidence(A \rightarrow B)}{P(B)}=\frac{P(A \cap B)}{P(A)P(B)}
$$
Confidence is the condiction that A's propobility when B is occured.
Lift means that A and B disjoint proportion in the universe.


we take acupoints that's confidence were higher than 80%.If we chose too small, our data will too complicate.However, if chose too hight, it will too barren. we recursive it to layer three. We draw it as a chart.


## 3. Result


![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_baf5a13b3b165c3c704dbdfb443d9822.png)

Fig.1 Distribution of acupoints used in the retrieved.

### 3.3. . Apriori Algorithm-Based Association Rule Analysis for Item Sets of Acupoint Combinations.

We investigated 3960 association rules based on the acupoints datas.(See Table.1) and delete the data whose support or confidence are too small. The association rules were shown on the fig.1. The chart shows each acupoints' Support which is grater than 30%. We see that `Extra12` and `TF4` have most frequence in this data. We based on this to find confidence and lift for each other. The top 10 association rules of acupoints listed in Fig.2. We plot it into 3-dimension chart(Fig.3). We can see the scatter in the space.
With respect to the grouped item sets, we used graphbased visualization by color or size. +e features were visually presented based on a grouped matrix of 10 association
rules (Fig.4).

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b0f636145739afde3957f95ca4b39f2c.png)




Fig.2 acupoints's support, confidence and lift for top 10 supprot of layer 2.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_4e6c3e24d4c5e87d8ec34b72292b2c21.png)
Fig.4 Scatter plot for 17 rules.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_393a9977b2dacbbccbeebab427946ddf.png)





Fig.3 Grouped matrix for 16 association rules.

In 2-3, we show that if its lift is more higher, then its association is more related.


This matrix means that if support and lift are more large, the circle size will be more big and red. Otherwise, it will turn small and white. In this table we see that `LI4,ST36->ST44` and `LI4, ST44->ST36` and `ST36,ST44-> LI4` have highly support and lift. This assocition rules were consistent for rule  `LI4,ST36->ST44` and `LI4, ST44->ST36` and `ST36,ST44-> LI4` .



## 4. Discussion
Our results indicated that  `LI4,ST36->ST44` and `LI4, ST44->ST36` and `ST36,ST44-> LI4`  were the core acupoint combinations in this data.

## 5. Conclusions

the acupoint combination of  `LI4,ST36->ST44` and `LI4, ST44->ST36` and `ST36,ST44-> LI4`  could be considered the core acupoint combinations for this data.


## Reference

[1] Xia, P., et al., Data Mining-Based Analysis of Chinese Medicinal Herb Formulae in Chronic
Kidney Disease Treatment. Evidence-based Complementary and Alternative Medicine, 2020. 2020(2):
p. 1-14.













----





### code

``` python=1
class data:
    def __init__(self,name,cset):
        self.name=name
        self.fequence=0
        self.countset=cset
        self.persentage=0
        self.confidence=[]
    def calcf(self):
        self.persentage=self.fequence/number
    def calccon(self,a,b,n):
        c=0
        l=len(b)
        la=len(a)
        a.sort()
        b.sort()
        y=0
        for i in savedata[l-1]:
            if b==i.countset:
                c=self.persentage/i.persentage
                y=i.persentage
                #li=c/i.persentage
                break
        for i in savedata[la-1]:
            if a==i.countset:
                li=c/i.persentage
        self.confidence+=[confidence(str(b)+"=>"+str(a),c,li)]



        

class confidence:
    def __init__(self,name,con,lift):
        self.name=name
        self.con=con
        self.li=lift
    
        
    

def fractal(n):
    if n<=1: return 1
    else: return n*fractal(n-1) 


def selectdata(data,target):
    result = True
    for i in data:
        if i not in target:
            result = False

    return result

def conbination(data1,data2):
    _result=data1.copy()

    for i in data2:
        if i not in _result:
            _result+=[i]
    _result.sort()
    s=""
    s+="["
    for i in range(len(_result)-1):
        s+=str(testdatan[_result[i]])+","
    s+=str(testdatan[_result[-1]])+"]"
    result=data(s,_result)
    return result

def initialize():
    for i in range(len(testdatan)):
        savedata[0]+=[data(testdatan[i],[i])]
less=0.3
testdataname=[["Extra12","TF4","LI4","LI11","ST25","ST36","ST44"],["Extra12","TF4","LI4","LI11","ST25","ST36","ST44"],["Extra12","TF4","LI4","LI11","ST25","ST36","ST44"],["TF4","CO4","Extra12","CO18"],["TF4","CO4","Extra12","CO1","HX1","CO17"],["LI4","HT7","ST36","ST44","SP6"],["TF4","CO4","Extra12","CO18"],["ST25","GB28","RN12","RN9","RN4","SP6"],["TF4","CO4","CO13","Extra12","CO18"],["ST25","GB28","REN12","REN9","REN4","SP6","TF4","CO4","Extra12","CO1","HX1","CO17"],["LI4","LI11","ST36","ST44","LR3"]]
testdatan=[]
testdata=[[] for i in range(len(testdataname))]
for i in testdataname:
    for j in i:
        if j not in testdatan:
            testdatan+=[j]
for i in range(len(testdataname)):
    for j in range(len(testdataname[i])):
        for k in range(len(testdatan)):
            if testdataname[i][j] == testdatan[k]:
                testdata[i] += [k]

#testdata=[[1,2,3,4],[2,3,5],[1,2,3,5],[2]]
number=len(testdata)
savedata=[[],[],[]]
initialize()
print(testdatan)
for m in range(2):
    #calculate fequence
    for i in savedata[m]:
        for j in testdata:
            if selectdata(i.countset,j):
                i.fequence+=1
        i.calcf()

    # delete low fequence
    for i in range(len(savedata[m])-1,-1,-1):
        if savedata[m][i].persentage<less:
            del savedata[m][i]
    # new ieration
    for i in range(len(savedata[m])-1):
        for j in range(i+1,len(savedata[m])):
            con=conbination(savedata[m][i].countset,savedata[m][j].countset)
            savedata[m+1]+=[con]       
#calculate fequence
for i in savedata[2]:
    for j in testdata:
        if selectdata(i.countset,j):
            i.fequence+=1
    i.calcf()
for i in range(len(savedata[2])-1,-1,-1):
        if savedata[2][i].persentage<less:
            del savedata[2][i]

label=[]
for i in range(len(savedata[2])-1,0,-1):
    for j in range(i-1,-1,-1):
        if j in label: continue
        if savedata[2][i].name == savedata[2][j].name:
            label+=[j]
label.sort()
print(len(savedata[2]))
print(label)
for i in range(len(label)-1,-1,-1):
    del savedata[2][label[i]]
for i in savedata[0]:
    print(i.name,i.persentage)    

for i in range(len(savedata[1])):
    savedata[1][i].calccon([savedata[1][i].countset[0]],[savedata[1][i].countset[1]],1)
    savedata[1][i].calccon([savedata[1][i].countset[1]],[savedata[1][i].countset[0]],1)
conset=[[0,1,2],[1,2,0],[2,0,1]]
for i in savedata[2]:
    for j in conset:
        i.calccon([i.countset[j[0]]],[i.countset[j[1]],i.countset[j[2]]],2)
        i.calccon([i.countset[j[0]],i.countset[j[1]]],[i.countset[j[2]]],2)
for i in savedata[2]:
    print(i.name)
    print(i.persentage)
    for j in range(6):
        print(i.confidence[j].name,i.confidence[j].con,i.confidence[j].li)
    ```

