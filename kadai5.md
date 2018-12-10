
# 課題5レポート

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

判別分析法によって対象物の濃度と背景の濃度がそれぞれ最もよくまとまるような2値化の閾値を計算する。

閾値tで画像を二つのクラスに分けたとき、その2つのクラスのクラス間分散の各クラス内分散に対する比の値が最も大きくなるようにtの値を求める。

まず、閾値をiとしたとき、ヒストグラムを2つのクラスに分け、C1、C2にそれぞれ代入する。  
C1 = H(1:i);  
C2 = H(i+1:256);   

続いて、それぞれのクラスの画素数、平均値、分散を計算し、変数に代入する。  
n1 = sum(C1); %画素数の算出  
n2 = sum(C2);  
myu1 = mean(C1); %平均値の算出  
myu2 = mean(C2);  
sigma1 = var(C1); %分散の算出  
sigma2 = var(C2);  

次に、クラス内分散とクラス間分散を計算する。  
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出  
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出  

最後にクラス内分散とクラス間分散の比を求め、今までの値よりも大きければ保持する。  
if max_val<sigma_B/sigma_w  
max_val = sigma_B/sigma_w;  
max_thres =i;  

以上の処理をすべての閾値のパターンで行い、最適な閾値を求める。


IMG = ORG > max_thres;  
imagesc(IMG); colormap(gray); colorbar;  
pause;  

によって、求めた閾値を使った2値化を行う。図3に結果を示す。
![判別法による2値化](https://github.com/muinus/lecture_image_processing/blob/master/kadai5/kadai5_1.JPG?raw=true)   
図3 判別分析法による2値化画像
