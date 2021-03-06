# Chapter 1 變數(Variable)
###### tags: `python` `mcl` `program`
## 變數(variable)和類別(type)

在程式中，變數是一種儲存數據的載體。計算機中的變量是實際存在的數據或者說是儲存器中儲存數據的一塊內存空間，變數的值可以被讀取和修改，這是所有計算和控制的基礎。計算機能處理的數據有很多種類別，除了數值之外還可以處理文本、圖形、音訊、影像等各種各樣的數據，那麼不同的數據就需要定義不同的存儲類型。 Python中的數據類型很多，而且也允許我們自定義新的數據類別（這一點在後面會講到），我們先介紹幾種常用的數據類別。

* 整數 (integral)：Python中可以處理任意大小的整數（Python 2.x中有int和long兩種類型的整數，但這種區分對Python來說意義不大，因此在Python 3.x中整數只有int這一種了），而且支持二進制（如0b100，換算成十進制是4）、八進制（如0o100，換算成十進制是64）、十進制（100）和十六進制（0x100，換算成十進制是256）的表示法。

* 浮點數 (float)：浮點數也就是小數，之所以稱為浮點數，是因為按照科學記數法表示時，一個浮點數的小數點位置是可變的，浮點數除了數學寫法（如123.456）之外還支持科學計數法（如1.23456e2）。

* 字串 (string)：字串是以單引號或雙引號括起來的任意文本，比如'hello'和"hello",字符串還有原始字符串表示法、字節字符串表示法、Unicode字符串表示法，而且可以書寫成多行的形式（用三個單引號或三個雙引號開頭，三個單引號或三個雙引號結尾）。

* 布林值 (boolean)：布林值只有True、False兩種值，要麼是True，要麼是False，在Python中，可以直接用True、False表示布林值（請注意大小寫），也可以通過布林運算計算出來（例如 3 < 5 會產生布林值True，而 2 == 1 會產生布林值False）。

## 變量命名
對於每個變量我們需要給它取一個名字，就如同我們每個人都有屬於自己的響亮的名字一樣。在Python中，變量命名需要遵循以下這些必須遵守的硬性規則和強烈建議遵守的非硬性規則。

* 硬性規則：
  1. 變數名由字母（廣義的Unicode字符，不包括特殊字符）、數字和下劃線構成，數字不能開頭。
  2. 大小寫敏感（大寫的a和小寫的A是兩個不同的變數）。
  3. 不要跟關鍵字（有特殊含義的單詞，後面會講到）和系統保留字（如函數、模塊等的名字）衝突。
* PEP 8要求：
  1. 用小寫字母拼寫，多個單詞用下劃線連接。
  2. 受保護的實例屬性用單個下劃線開頭（後面會講到）。
  3. 私有的實例屬性用兩個下劃線開頭（後面會講到）。

當然，作為一個專業的程式員，給變數（事實上應該是所有的標識符）命名時做到見名知意也是非常重要的。(詳見此篇 https://docs.mcl.math.ncu.edu.tw/books/weekly-meeting/page/week-16-code-review)

## 程式範例
第一個程式
``` python=1
print("Hello World!") # Hello World!
```
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_26333e9aac46e70bb1c9ce4c1376c811.png)

在程式中，"="所代表的意義為賦予變數一個值，例如 n=1 意思就是賦予 n 這個變數為1，若要相當於數學上等號的意義，符號應為 "==" (下一章節會講到)。

python 中 print() 是一個函數，他可以印出你輸入的數字，例如print("123")，結果應為 123
type()函數可以檢查輸入的變數類別。
``` python=1
# 井字後方的文字為註解，在運行程式碼的時候不會讀取此段
"""
若想註解多行文字可使用三個雙引號前後包夾
"""
n=100
m=3.124
l=True
k='hello world'
print(type(n)) #<class 'int'> 
print(type(m)) #<class 'float'> 
print(type(l)) #<class 'bool'> 
print(type(k)) #<class 'str'> 
```
結果如下:
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_477fa5fd2f0906231ea80c61eadfbf28.png)



