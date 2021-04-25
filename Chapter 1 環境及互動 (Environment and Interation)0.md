# Chapter 1 環境及互動 (Environment and Interation)
###### tags: `processing` `mcl` `program`
Processing 在執行程式時，需要用一些函數包裝起來(更詳細的函數會在後面的章節提到)，例如 `setup`、`draw` 等。

``` processing=1
void setup(){
  程式碼1...
  //裡面的程式只會在開始的時候執行一次。
}

void draw(){
  程式碼2...
  //裡面的程式會在開始後不斷重複執行。
}
```
在執行程式前，需開啟畫布，執行的函數為 `size(width,height)`，執行下列程式後會出現以下視窗:
``` processing=1
void setup(){
  size(400,200);
}
```
請注意，打完一行程式碼結尾都必須加 ;
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_1d98b54904c241fd007c2a5f129217cf.png)


`size(width,height)`所開啟的畫布大小為 width*height(此例中為400x200)，單位為像素(pixel)。每一個像素都有它的座標，與一般不同的是，原點(0,0)為左上角，x軸往右用大，y軸往下越大。

`backgorund(color)`，此函數為設定背景色，所輸入的值必須為 RBG(例如 (255,0,0)為紅色，更詳細的RBG顏色可以上網查詢)
``` processing=1
void setup(){
  size(400,200);
  background(0); //若只填入一個數字則代表三個數字相同，(0)=(0,0,0)
}
```
效果如下
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_5024977bda48ce70e9840c5abfa628cd.png)

### draw

`draw` 會一直重複執行函數內的程式碼，可以使用`frameRate`來調整更新頻率，若沒有說明，默認更新頻率是60FPS。
```processing=1
void setup(){
  size(400,200);
}
void draw(){
  background(0);
}
```
`執行上述程式碼後，結果應該與前一個結果相同，雖然他有一直在更新畫布，但給他的程式碼只有黑色的背景色，所以當然看不出來有甚麼改變。`
### mousePressed
`mousePressed` 會在滑鼠點擊後觸發事件
```processing=1
void draw(){
}
void mousePressed(){
  println("Hello World");
}
```
點擊左鍵後應出現
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_f4b7895b77f4cffe1b9cf06dca497bd5.png)

### keyPressed
`keyPressed`類似`mousePressed`，他可以指定特定按鍵來觸發事件
```processing=1
void draw(){
}
void keyPressed(){
  if(key=='m'){ //按下m鍵
    println("Hello World");
  }
}
```
按下m鍵後，應與上圖相同。





