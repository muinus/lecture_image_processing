

# 課題8レポート

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

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai8/kadai8_1.JPG?raw=true)   
図2 白黒濃淡画像  

次に、以下のコードによって閾値が128の2値画像を生成する。

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

表示された2値画像を図3に示す。

![2値画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai8/kadai8_2.JPG?raw=true)   
図3 白黒濃淡画像の濃度ヒストグラム

続いて、二値化された画像の連結成分にラベルをつける。

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar;  

によって、ラベリングした連結部分にそれぞれ色を付けて表示する。
表示された画像を図4に示す。

![ラべリング画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai8/kadai8_3.JPG?raw=true)   
図4 ラベリングされた色付き画像

図4から上部の木々は一定間隔で連結が切れていることがわかる。
