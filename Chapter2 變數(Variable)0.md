# Chapter2 變數(Variable)
###### tags: `processing` `mcl` `program`
processing 語法完全參造java
## 宣告
在`processing`中，你可以宣告一些變數值來儲存你需要的資料，常用的變數類型(type)包括以下幾種:
1. 整數(int): 可細分為short整數（佔2個位元組）、int整數（佔4個位元組）與long整數（佔8個位元組）。不同長度的整數，可儲存的整數範圍也不同。long整數佔的記憶體長度比int整數來得多，可表示的整數範圍也就比int整數大。同樣的，int整數可表示的整數範圍也比短整數來得大。

2. 浮點數(float): 主要用來儲存小數數值，可分為float浮點數（佔4個位元組）與double浮點數（佔8個位元組），double浮點數使用的記憶體空間比float浮點數來得多，可表示的精確度也比較大。

3. 字串(String): String用來儲存多個字元，文字使用雙引號""來儲存。

4. 字元(Char): char型態用來儲存'A'、'B'、'林'等字元符號。在JDK8中，Java的字元採Unicode 6.2編碼，JVM實作採UTF-16 Big Endian，所以每個字元型態佔兩個位元組，中文字元與英文字元在Java中同樣都是用兩個位元組儲存。

5. 布林值(boolean): boolean型態可表示true與false，分別代表邏輯的「真」與「假」。在Java中不用在意boolean型態的長度，因為你也無法將boolean型態與其它型態作運算。

### 宣告的語法如下:

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_079a64a29dc20a8f5d3b3a36a6586bb8.png)


第一格放資料的型態，也就是上述所說
第二個放變數的名字
最後賦予變數一個值(有些型態若沒有設會自動設為0)


## 變數的生命週期
變數分為兩類，全域變數與區域變數，全域變數在當前的程式都可以被任一個區域使用，區域變數只能在當前的函數使用，要注意再命名的時候，區域變數盡量不要跟全域變數取相同的名字，避免混淆，若產生相同的名稱下，`processing`會優先使用區域變數。

## 變數命名規則
對於每個變量我們需要給它取一個名字，就如同我們每個人都有屬於自己的響亮的名字一樣。
* 硬性規則：
  1. 變數名由字母（廣義的Unicode字符，不包括特殊字符）、數字和下劃線構成，數字不能開頭。
  2. 大小寫敏感（大寫的a和小寫的A是兩個不同的變數）。
  3. 不要跟關鍵字（有特殊含義的單詞，後面會講到）和系統保留字（如函數、模塊等的名字）衝突。
* 非硬性規則:
  1. 類別以英文大寫字母開頭，若有多個英文單字組成，採取大寫駝峰型 (upper camel case)
  2. 方法或變數（包括參數、屬性等）以英文小寫字母開頭，若有多個英文單字組成，採取小寫駝峰型 (lower camel case)

```
UpperCamelCase //合法字
lowerCamelCase //合法字
3line //不合法
String //不推薦，容易混淆
```

### 範例1
``` processing=1
//在程式最前面宣告的為全域變數
int globalVariable = 0;
void setup(){
    //在函數宣告的為區域變數，只有此函數可以使用
    int localVariable = 1;
    print(globalVariable); // 0
    print(localVariable); // 1
}
void draw(){
    print(globalVariable); // 0
    print(localVariable); // error:localVariable cannot be resolved to a variable

}
```


### 範例2

``` processing=1
float ballpositionX=50;
float ballpositionY=100;
void setup(){
    size(200,200);
    background(0);
    fill(255); //將下方的圖形塗滿顏色，語法為 fill(顏色)
    circle(ballpositionX,ballpositionY,20); //circle函數可以在指定的座標畫一個圓
    //語法為circle (x座標,y座標,直徑)
}
//在(20,100畫一個半徑10的圓，並塗滿白色)
```
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_747b27223d6a2d6542b79fccb1dd66f7.png)

## 運算子(Operator)

程式語言中提供運算功能的就是運算子。
| 運算子     | 描述       |
| ---------- | ---------- |
| `[]` `[:]` | 下標，切片  |
| `**`       | 指數       |
| `~` `+` `-`| 取反, 正負號 |
| `*` `/` `%` `//` | 乘，除，模(mod)，整除|
| `+` `-` | 加，减|
| `>>` `<<` | 右移，左移 |
| `&` | 位與  |
| `^` `||`  |異或，位或|
| `<=` `<` `>` `>=`| 小於等於，小於，大於，大於等於 |
| `==` `!=` | 等於，不等於|
| `is`  `is not`| 身份運算子  |
| `in` `not in` | 成員運算子 |
| `not` `||` `&&` | 邏輯運算子 |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` `|=` `^=` `>>=` `<<=` |賦值運算子|


比較運算子有的地方也稱為關係運算子，包括`==`、`!=`、`<`、`>`、`<=`、`>=`，我相信沒有什麼好解釋的，大家一看就能懂，唯一需要提醒的是比較相等用的是`==`，請注意這個地方是兩個等號，因為`=`是賦值運算子，我們在上面剛剛講到過，`==`才是比較相等的比較運算符。比較運算符會產生布林值，要麼是`true`要麼是`false`。

### 範例1
``` processing=1
void setup(){
    int a=100;
    int b=200;
    print(a+b); // 300
    print(a-b); // -100
    print(a%7) //2
    print(a==b) //false
    print(a<b) //true
    print(true && false) //false
    //好好學基數
}
```

### 範例2
```processing=1
float positionX=0;
float positionY=100;
void setup(){
    size(200,200);
}
void draw(){
    background(0);
    circle(positionX,positionY,20);
    positionX+=5; // += 代表說將前面的值加上後面的數字，等同於positionX=positionX+5
    //若positionX現在等於5，做完運算後會等於5+5=10
}
```
效果如下:
<img src="https://media.giphy.com/media/SUvHcYgQBpt0dcicOf/giphy.gif"></img>

可以注意的是`draw`是一個會不斷重複執行的函數，所以她會不斷重複執行裡變得程式碼，可以把它想成時間的推移，所以positionX的數值會不斷地更新並且+5，進而更新圓的位置。

注: 可以想想若把background(0)放在`setup`裡面會發生甚麼事情。




