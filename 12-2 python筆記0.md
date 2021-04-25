# 12/2 python筆記
###### tags: `python` `math`
1.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_52924a0fcb2a05f42041a00b97b44d36.png)


```python=1
n=int(input())
for i in range(3):
    for j in range(n):
        for k in range(3):
            if(i-k==0 or i+k==2): #直線方程式
                print(str((3*i+k+2)//2)*n,end='') #因為是每兩隔+1，所以要//2
            else:
                print(" "*n,end='')
        print()

```

2.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b6abeab5e56ad888be37360a65161848.png)

```python=1
n=int(input())
for i in range(3):
    for j in range(n):
        for k in range(3):
            if(i-k==0 or i+k==2):
                if(j==0 or j== n-1): #一樣，只是在j!=0 || j!=n-1的時候寫法不一樣
                    print(str((3*i+k+2)//2)*n,end='')
                else:
                    print(str((3*i+k+2)//2)+" "*(n-2)+str((3*i+k+2)//2),end='')
            else:
                print(" "*n,end='')
        print()
```

3.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_90779a0a95e5bf6fcab45956a34bc21a.png)


```python=1
n=int(input())
midnum=n//2
for i in range(3):
    for j in range(n):
        for k in range(3):
            if(i-k==0 or i+k==2):
                if(j==midnum): #中心數=n//2，然後要注意各層需要印神麼
                    print(" "*midnum+"x"+" "*midnum,end='')
                elif(j<midnum):
                    print(" "*j+"\\"+" "*((midnum-j)*2-1)+"/"+" "*j,end='')
                else:
                    print(" "*(n-j-1)+'/'+" "*((j-midnum)*2-1)+"\\"+" "*(n-j-1),end='')
                
            else:
                print(" "*n,end='')
        print()
       


```


4.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_c800716e59b10dc9c707c89794f6b31e.png)

``` python=1
n=int(input())
for i in range(2*n-1):
    for j in range(n):
        if(i-j==n-1): #注意甚麼範圍需要印甚麼東西
            print(str(j)*n,end=' ')
        elif(i-j>n-1 or i-j<0): #這個範圍以外都印空白
            print(" "*n,end=' ')
        else://剩下的部分
            print(str(j)+" "*(n-2)+str(j),end=' ')
    print()

```

5.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_99fc38394abc324a2700d486d2478767.png)



``` python=1
n=int(input())
for i in range(-n+1,n)://另中心為0比較好寫
    for j in range(-n+1,n):
        print(n-max(abs(i),abs(j)),end=' ')//n要剪掉離中心的距離，距離為 norm_max
    print()
       
```


6.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_25e5551bbb0c73f4359a78cd91092e6a.png)


``` python=1
n=int(input())
for i in range(-n+1,n):
    for j in range(-n+1,n):
        if(abs(i+j)<=n-1 and abs(i-j)<=n-1): #運用你的數學思維算出邊界是多少吧
            print(n-max(abs(i),abs(j)),end=' ')
        else:
            print(" ",end=' ')
    print()
       

```

7.![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_272b8fafc7d862cd74b95df0fe5d12c7.png)
``` python=1
for n in range(2,100): #從2到99
    i=2
    print(n,"=",end=' ')
    while True:
        if(n%i==0): #如果整除那就印出來然後除掉
            n=n//i
            if(n==1): #如果=1表示到底了要出迴圈
                print(i,end='')
                break
            else: #不然就繼續做
                print(i,"x",end=' ')
        else: #無法整除就找下一個質因數
            i+=1
    print()
```
8.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_37346a21edcb0de09491a73422e01d55.png)
``` python=1
for n in range(2,101):
    f=False
    for j in range(2,n-1): #從2一路判斷到n-1
        if(n%j==0): #如果整除 表示他不是質數
            f=True
    if(f==False): print(n,end=' ')
```

9.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_5b68c1f36c4458b6db5dab00acc51300.png)

``` python=1
for i1 in range(1,9):
    for i2 in range(9):
        for i3 in range(9):
            for i4 in range(9):
                for i5 in range(9): #每個數字跑一輪
                    n=i1*10000+i2*1000+i3*100+i4*10+i5
                    if((n*i1)%111111==0): #每個數字都一樣=可以被111111整除
                        print(n,i1,n*i1)
                        
                        
```
# 12/15
## 對酒當歌
``` python=1
s="對酒當歌人生幾何譬如朝露去日苦多慨當以慷憂思難忘何以解憂唯有杜康青青子衿悠悠我心但爲君故沉吟至今呦呦鹿鳴食野之苹我有嘉賓鼓瑟吹笙明明如月何時可掇憂從中來不可斷絕越陌度阡枉用相存契闊談宴心念舊恩月明星稀烏鵲南飛繞樹三匝何枝可依山不厭高海不厭深周公吐哺天下歸心"
for i in range(5):
	for j in range(3):
		print("|",end='')
		for k in range(7,-1,-1):
			for l in range(2,-1,-1):
				if((j==2 or (k%2==1 and i==0) or (k%2==0 and i==4)) and l!=0):
					print("  ",end='')
				elif(l==0):
					print("|",end='')
				else:
					print(s[4*(i-k%2)+16*k+j+2*(l-1)],end='')				
			print("",end="")
		print()
        

```
## ww
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_067c08aead7459396954a3111e65a857.png)

``` python=1
n=int(input())
for i in range(n+1):
	for j in range(2):
		for w in range(2):
			for l in range(-n+1+w,n):
				s=n-1-abs(l)
				if(i==s or i==s+1):
					print(str(n-abs(l))*3,end=' ')
				else:
					print(" "*3,end=' ')
		print()
```
## ??
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_c0f955ab949537742c5be93d11759365.png)


``` python=1
n="1"
count=0
for k in range(5):
	s=""
	for i in range(len(n)):
		count+=1
		if(i==len(n)-1 or n[i] != n[i+1]):		
			s+=str(count)+str(n[i])
			count=0		
	print(s)
	n=s
```



