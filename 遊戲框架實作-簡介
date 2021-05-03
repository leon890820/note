# 遊戲框架實作
###### tags: `game` `java`

## 碰撞器(collider)

### 0.簡介
碰撞在遊戲中常常使用，如果需要判斷兩個物體是否有發生碰撞，就可以使用碰撞器來檢測是否有發生碰撞，這次要來介紹的主題是分離軸碰撞檢測(Separating Axis Theorem, SAT)。下面就一一介紹如何實現此方法。

### 1.AABB碰撞檢測

此方法可以套用到任何凸多邊形的形狀，先以長方形為例，圖1-1可以看到，如果兩個物體之間沒有發生碰撞，一定存在一條分離軸來分開兩個物體，反過來說，若物體發生碰撞，則找不到任一角度的分離軸使物體分開，那我們要怎麼找到分離軸呢?先來看一個特殊例子，圖1-2可以看到若兩個物體沒有發生碰撞，則$$A.max < B.min || B.max<A.min \quad\quad (1)$$ 因為B可能在A的左邊。

<img src='https://i.imgur.com/lszVB38.png' width=350>
<img src='https://i.imgur.com/fXwsl8l.png' width=350>



**圖1-1 兩個沒有碰撞的物體一定可以找到分離軸** &emsp;&emsp;  **圖1-2 A.min 為矩形A在所有頂點中最小的**

所以我們需要找任意一個向量並投影到上面來判斷物體是否發生碰撞(圖1-3)，但這樣會花費許多的資源及時間，其實我們不需要每一個方位都去檢查，由圖中可以看到，若兩物體沒有碰撞，必定存在一條分離軸與A或B的邊平行，我們可以只檢查物體邊的法向量即可(圖1-4)。


<img src='https://i.imgur.com/yJIpzCi.png' width=450>
<img src='https://i.imgur.com/XwOKzOA.png' width=200>

&emsp;&emsp;&emsp; **圖1-3 投影到任意一條向量上** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; **圖1-4 多邊形其中一邊的法向量**

### 2.向量





