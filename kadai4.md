# 課題4レポート

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


画素の濃度ヒストグラムを作成するためにMATLABの関数imhist()を使用した。

imhist(ORG); 

によって、表示した結果を図3に示す．

![ヒストグラム](https://github.com/muinus/lecture_image_processing/blob/master/kadai4/kadai4_1.JPG?raw=true)   
図3 画素の濃度ヒストグラム 
