
# 課題7レポート

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

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai7/kadai7_1.JPG?raw=true)   
図2 白黒濃淡画像  

次に、白黒濃淡画像の濃度ヒストグラムを表示する。

imhist(ORG);

によって、表示されたヒストグラムを図3に示す。

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai7/kadai7_2.JPG?raw=true)   
図3 白黒濃淡画像の濃度ヒストグラム

続いて、白黒濃淡画像のダイナミックレンジを広げる。

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  

によって、白黒濃淡画像の諧調をダイナミックレンジが255になるようにする。変更した画像を図4に示す。

![変更画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai7/kadai7_3.JPG?raw=true)   
図4 ダイナミックレンジが255の白黒濃淡画像

最後に、上記画像の濃度ヒストグラムを表示する。

ORG = uint8(ORG);
imhist(ORG);

unit8()関数は引数の中身が行列の場合、配列の要素を要素間の比を保ったまま最大値が255の整数となるように値を変換する。これによって、作成されるヒストグラムの範囲が0-255となり、図3のヒストグラムと比較が容易となる。表示されたヒストグラムを図5に示す。

![ヒストグラム](https://github.com/muinus/lecture_image_processing/blob/master/kadai7/kadai7_4.JPG?raw=true)   
図4 ダイナミックレンジが255の白黒濃淡画像のヒストグラム
