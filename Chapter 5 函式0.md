# Chapter 5 函式
###### tags: `processing` `mcl` `program` `mrl`

函式是Processing的基本建構單元，之前舉的例子中都已經常常使用函式了，例如`size()`,`background()`等等，本章主要介紹如何自己建構一個函式。函式的威力在於模組化(Modular)，就像堆樂高一樣，每個積木都有自己的用途，厲害的是你可以用同一個積木去堆出不同的東西例如摩天大樓。

如果你想反覆畫出一朵花或更複雜的東西，那麼函示會很有用處，你建構完花的函式之後你只需要使用`flower()`就可以畫出一朵花，不需要著墨在畫出花的細節，讓你可以去做更高階的事情。

## 建構函式

執行主程式的時候若遇到函式，他會先跳到函式裡的程式碼處理再回到原本的主程式。

``` processing=1
void setup(){
    println("I'm in setup");
    printFunction();
    println("I'm in setup");
}
void printFunction(){
    print("I'm in function");
}
```
以上執行結果應為
`I'm in setup`
`I'm in function`
`I'm in setup`

撰寫函式分為三個部分`回傳值`、`名稱`及`參數`，
```
return name(argument){
    staement
}
```
若沒有回傳值則使用 `void` 來當回傳值，意為空。若無參數則括號內不填東西，我們舉下列幾個例子來實做看看

### 沒有回傳值且沒有參數

已丟骰子為例

```
void setup(){


}
void rollDice(){
    println(random())


}

```






