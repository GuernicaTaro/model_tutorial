# Self-Organizing Map

自己組織化マップ(Self-Organizing Map, SOM)は、データ空間から、より低次元の特徴空間（２次元や３次元にすることが多い）への写像を構成するアルゴリズム。
データ構造の似ているクラスタのデータ点を、特徴空間において近くに配置することから、データの幾何学的な性質を保った低次元化ができると言われる。
可視化やクラスタリングに用いることができる。

## Case 1

アイリスのデータセットにSOMを適用してみた。

[som_iris.png](https://github.com/GuernicaTaro/model_tutorial/blob/self-organizing_map/self-organizing_map/case1_iris/model/som_iris.png)
は、SOMで作ったマップをラベルとともに表示したもの。SOMはラベルの情報を使わずにマップを構成するが、同じラベルのデータは近くにマップされているのがわかる。
色はU-matrixを表しており、これは[wikipedia](https://en.wikipedia.org/wiki/U-matrix)によるとノード間のユークリッド距離らしい。SOMではデータを格子に写像するが、もともとのデータ間の距離を色で表しているということかと思う。

## Case 2

原理的に二次元平面では表せないデータ構造に対する結果を見る目的で、からまったリング状にデータを配置してSOMを適用してみた。

[som_rings.png](https://github.com/GuernicaTaro/model_tutorial/blob/self-organizing_map/self-organizing_map/case2_rings/model/som_rings.png)
をみると、ラベル2のデータが左右に切り離されているのがわかる。

## Case 3

MNISTデータセットにSOMを適用してみた。

[som_digits.png](https://github.com/GuernicaTaro/model_tutorial/blob/self-organizing_map/self-organizing_map/case3_digits/model/som_digits.png)
をみると、同じ数字は固まって配置されているのがわかる。また、6と0と9など、似た数字は近くに配置されており、「データ構造の似ているクラスタのデータ点を、特徴空間において近くに配置する」というSOMの性質が確認できる。

## Case 4

Swiss Rollのデータを生成し、SOMを適用してみた。

[som_swissroll.png](https://github.com/GuernicaTaro/model_tutorial/blob/self-organizing_map/self-organizing_map/case4_swissroll/model/som_swissroll.png)
をみると、Swiss Rollを展開できていないのがわかる。しかし、[wikipedia](https://en.wikipedia.org/wiki/Self-organizing_map)では似たようなフィッティングに成功しているので、もう少し工夫すれば展開できるかも。


## 参考記事
- まとめ : https://qiita.com/ae14watanabe/items/7c70924798c8125c05eb
- 実装 : https://www.haya-programming.com/entry/2018/04/07/161249
- わかりやすい解説文書 : http://www.brain.kyutech.ac.jp/%7Efurukawa/data/SOMtext.pdf

## 他の低次元化アルゴリズム
- PCA : 線形変換で分散最大化して特徴を抽出する。
- MDS : データ同士の距離を入力すると、近くのものを近くに配置してくれる。https://yuki-koyama.hatenablog.com/entry/2015/07/13/015736#f-6813c7f4
- t-SNE : 局所的な構造を捉えるのが得意。https://qiita.com/g-k/items/120f1cf85ff2ceae4aba
