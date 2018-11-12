# 課題2レポート

フリー素材アイドル「MIKA☆RIKA」 http://mika-rika-free.jp/ よりダウンロードしたフリー画像を原画像とする．
この画像は縦1084画像，横1692画素によるディジタルカラー画像である．

ORG=imread('org.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_1.JPG?raw=true)   
図1 原画像


まずは原画像を白黒濃淡画像に変換する。

ORG = rgb2gray(ORG);  

によって、白黒濃淡画像に変換し、表示した結果を図2に示す．

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai3/kadai3_1.JPG?raw=true)   
図2 白黒濃淡画像


閾値処理とは、輝度値が一定以上の画素を1、それ以外の画素を0とする2階調画像を生成する処理である。  
このため、課題2と同様に、この白黒濃淡画像を2つの値に分ければよい。いま、画像は256階調なので、
まずは閾値を64とする閾値処理画像を以下のように生成する。

IMG = ORG>64;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

表示した結果を図3に示す．

![閾値64画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai3/kadai3_2.JPG?raw=true)   
図3 閾値を64とする閾値処理画像


次に閾値を96とする閾値処理画像を以下のように生成する。

IMG = ORG>96;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

表示した結果を図4に示す．

![閾値96画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai3/kadai3_3.JPG?raw=true)   
図4 閾値を96とする閾値処理画像


次に閾値を128とする閾値処理画像を以下のように生成する。

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

表示した結果を図5に示す．

![閾値128画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai3/kadai3_4.JPG?raw=true)   
図5 閾値を128とする閾値処理画像


最後に閾値を192とする閾値処理画像を以下のように生成する。

IMG = ORG>192;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

表示した結果を図6に示す．

![閾値192画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai3/kadai3_5.JPG?raw=true)   
図6 閾値を192とする閾値処理画像
