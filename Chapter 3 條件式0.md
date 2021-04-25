# Chapter 3 條件式
###### tags: `mcl` `processing` `program`

條件式是一種分支結構，在寫程式時，常常會發生不同條件所要判斷不同狀況，這時候就需要使用條件式，使用的方法如下:
## if 
最基本最常用的條件式，語法如下
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_c6e7fc2d6d9f01c02551f8773e043430.png)
if 裡面放的是布林值，若布林值為true，則會執行後面大括號的程式。

## if...else

與 if 相同，若括號裡的值為 true 則執行下列程式，否則執行else 裡的程式。

``` java=1
void setup(){
  if(3+5==7){//flase
    //code1
  }
  else{
    //code2
  }
}
```

上列程式會執行code2，因為3+5==7 是 false

## if...else if...else

與上述相似，如果 if 條件為false 則判斷下一個 else if 的條件，若都為 false 則執行else 的程式。

``` java=1
void setup(){
val=75;
  if(val>=90){//flase
    //code1
  }
  else if(val>=80){
    //code2 
  }
  else if(val>=70){
    //code3 
  }
  else{
    //code4
  }
}
```
上列程式會執行code3，因為val>=70 但<80 


## 範例

改造上一章的程式，使得球碰到邊緣時可以反彈

``` java=1
float ballX;
float ballY;
float ballVelocityX;
float ballVelocityY;
// Initialize ball's position and velocity
void setup(){
  size(400,400);
  ballX=random(width);
  ballY=random(height);
  ballVelocityX=random(-5,5);
  ballVelocityY=random(-5,5);
}
void draw(){
  background(0);
  circle(ballX,ballY,20);
  ballX+=ballVelocityX;
  ballY+=ballVelocityY;
  // If hit the wall, reverse its velocity
  if(ballX>width||ballX<0){
    ballVelocityX*=-1;
  }
  if(ballY>height||ballY<0){
    ballVelocityY*=-1;
  }
}
```
<iframe src="https://editor.p5js.org/leon890820/embed/nsi7ASN1c" style="
    width: 400.99306px;
    height: 400.99306px;
    border-width: 0px;
"></iframe>






