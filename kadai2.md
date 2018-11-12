# 課題2レポート

フリー素材アイドル「MIKA☆RIKA」 http://mika-rika-free.jp/ よりダウンロードしたフリー画像を原画像とする．
この画像は縦544画像，横827画素によるディジタルカラー画像である．

ORG=imread('ex1.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_1.JPG?raw=true)   
図1 原画像

まずは原画像を白黒濃淡画像に変換する。

ORG = rgb2gray(ORG);  

によって、白黒濃淡画像に変換し、表示した結果を図2に示す．

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai2/kadai2_1.JPG?raw=true)   
図2 白黒濃淡画像

2階調画像を生成するためには、この白黒濃淡画像を2つの値に分ければよい。いま、画像は256階調なので、
129-255の値の画素を集めた画像のみを黒として表示すれば2階調画像を作ることができる。

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

によって、2階調画像に変換し、表示した結果を図3に示す．

![2階調画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai2/kadai2_2.JPG?raw=true)   
図3 2階調画像

4階調画像を生成するためには、今度は白黒濃淡画像を4つの値に分ければよい。
0-64の値、65-128の値、129-192の値、193-255の値の画素を集めた画像に分けてそれぞれを重ね合わせて表示すると
4階調画像を作ることができる。

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

によって、4階調画像に変換し、表示した結果を図4に示す．

![4階調画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai2/kadai2_3.JPG?raw=true)   
図4 4階調画像

同様に、8階調画像を生成するためには、今度は白黒濃淡画像を8つの値に分ければよい。
for文を使用してプログラムを簡潔に記した。

IMG=0;  
for k = 1:8  
    IMG=IMG+(ORG>(32*k));  
end  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

によって、8階調画像に変換し、表示した結果を図5に示す．

![8階調画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai2/kadai2_4.JPG?raw=true)   
図5 8階調画像
