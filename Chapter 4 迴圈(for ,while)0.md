# Chapter 4 迴圈(for ,while)
###### tags: `processing` `mcl` `program` `mrl`

如果一個或一段程式碼需要重複執行時就需要使用到迴圈。例如需要在畫布中畫5個圓圈，如果不使用迴圈，程式碼會如下。

``` processing=1
void setup(){
    circle(random(width),random(height));
    circle(random(width),random(height));
    circle(random(width),random(height));
    circle(random(width),random(height));
    circle(random(width),random(height));
}
```
重複的程式碼使得整個專案不簡潔且雜亂，若使用以下程式碼:
``` processing=1
void setup(){
  for(int i=0;i<5;i+=1){
    circle(random(width),random(height));
  }
}
```
此程式碼執行結果與上個完全相同，但可以發現簡潔很多並省略很多重複步驟。

## for...

迴圈分為兩類 `for` 與 `while` 迴圈，`for`迴圈分為三個部分，1為宣告變數，2為執行條件，3為每次做完迴圈要做什麼事。 ` for(1;2;3) ` 中間用分號隔開`;`。以上面程式碼為例，1為 `int i=0` 意思是宣告一個i變數在`for` 迴圈裡面，為區域變數，2為`i<5` ，若`i<5`則執行迴圈裡的程式碼，3為 `i+=1` ，每做完一次迴圈`i`就`+1`。

## while

while 迴圈相對簡單，語法為 `while(boolean){//code}` 若 `while` 裡的bool為true，則執行程式碼。

## break

在迴圈裡面打`break;` 會強制跳出當前的迴圈。無法一次跳出多個迴圈。

## continue

在迴圈裡面打`continue;`會跳過當前階段迴圈。

## 範例1

``` processing=1
void setup(){
  size(600,600);
  background(0);
  for(int i=0;i<20;i+=1){
    circle(random(width),random(height));
  }
}
```


<iframe src="https://editor.p5js.org/leon890820/embed/CYlf31983" style="
    width: 400.99306px;
    height: 400.99306px;
    border-width: 0px;
"></iframe>

## 範例2

範例二示範了如何在迴圈裡再嵌套一個迴圈，這可以使你迴圈的數目增加，第一個迴圈重複了`cols`次 第二層迴圈重複了`rows`次，所以總共跑了`cols*rows`次，當然你也可以增加更多的迴圈在裡面，全看你怎麼設計這個程式。
``` processing=1
int scl=10;
int cols;
int rows;
void setup(){
  size(600,600);
  cols=width/scl;
  rows=height/scl;
}

void draw(){
  background(0);  
  noStroke();
  for(int i=0;i<cols;i+=1){
    for(int j=0;j<rows;j+=1){
    fill(random(255));
      rect(i*scl,j*scl,scl,scl);
    }  
  }
}
```
<iframe src="https://editor.p5js.org/leon890820/embed/PS-b-oJw7" style="
    width: 400.99306px;
    height: 400.99306px;
    border-width: 0px;
"></iframe>


比較多人疑惑的是`draw()` 與 `for` 差別在哪裡，可以把 `draw()`想成是時間的推移，`for`是數量的呈現。`draw()`會把函數裡的程式碼都執行完後才把圖畫出來。以範例二來說，他會把所有的`rect`一次畫出來，總共有 cols* rows個(可以思考一下為什麼)。而且每次更新都會畫出不同的顏色。

