##### フルスタックコース  

```
Railsにおける、「単数」と「複数」の使い分けについての説明です。

例えばコントローラー作成時は"blogs"と、モデル作成時は"blog”とそれぞれパラメーター指定させています。それに基づいて様々な変数等が自動的に作成されているようなので、"blogs"と"blog"を使い分けることに意味があるのだと思うのですが、何処にも記載が無いので未だに混乱しています。

rake routes"を行ってみても、Prefixに"blog"　”new_blog"もあれば、"blogs" "confirm_blogs"もあります。何故こうなっているのか全く理解できていません。

```

## 解答例
```
プログラミング言語には「命名規則」というものが存在します。そしてその規則は言語ごとによって異なります。質問者様が疑問に思っているのは「モデル」と「コントローラー」の命名規則についてだと思います。
以下に、railsの「命名規則」についてまとめるので覚えておいてください。これは「こういう決まり」として使っているうちに覚えていくしかないです。
```
***モデル***  　　
<table>
    <tr>
        <td><単一語></td>
        <td></td>
        <td></td>
        <td><複数語></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>名称</td>
        <td>例</td>
        <td>使用法</td>
        <td>名称</td>
        <td>例</td>
        <td>使用法</td>
    </tr>
    <tr>
        <td>モデル名</td>
        <td>user</td>
        <td></td>
        <td>モデル名</td>
        <td>user list</td>
        <td></td>
    </tr>
    <tr>
        <td>モデルクラス名</td>
        <td>User</td>
        <td>先頭大文字・単数形</td>
        <td>モデルクラス名</td>
        <td>UserList</td>
        <td>先頭大文字・単数形・キャメル</td>
    </tr>
    <tr>
        <td>ファイル名</td>
        <td>user.rb</td>
        <td>先頭小文字・単数形</td>
        <td>ファイル名</td>
        <td>user_list.rb</td>
        <td>先頭小文字・単数形・スネーク</td>
    </tr>
    <tr>
        <td>テーブル名</td>
        <td>users</td>
        <td>先頭小文字・複数形</td>
        <td>テーブル名</td>
        <td>users_lists</td>
        <td>先頭小文字・複数形・スネーク</td>
    </tr>
</table>

***コントローラー***  　　
<table>
    <tr>
        <td><単一語></td>
        <td></td>      
        <td></td>        
        <td><複数語></td>
        <td></td>
        <td></td>      
    </tr>
    <tr>
        <td>名称</td>
        <td>例</td>
        <td>使用法</td>
        <td>名称</td>
        <td>例</td>
        <td>使用法</td>
    </tr>
    <tr>
        <td>コントローラー名</td>
        <td>items</td>
        <td>先頭小文字</td>      
        <td>コントローラー名</td>
        <td>member_post</td>
        <td>先頭小文字・スネーク</td>      
    </tr>
    <tr>
        <td>コントローラークラス名</td>
        <td>ItemsController</td>
        <td>先頭大文字・キャメル</td>      
        <td>コントローラークラス名</td>
        <td>MemberPostController</td>
        <td>先頭大文字・キャメル</td>      
    </tr>
    <tr>
        <td>ファイル名</td>
        <td>items_controller.rb</td>
        <td>先頭小文字・スネーク</td>      
        <td>ファイル名</td>
        <td>member_post_contoroller.rb</td>
        <td>先頭小文字・スネーク</td>      
    </tr>
</table>

```
rails generateコマンドは、キャメルケースでもスネークケースでもどちらでも良いです。
*キャメルケースとは要素語の頭文字を大文字で表現する方法です。
*スネークケースとはアンダースコア（_）を区切記号として単語をつなげる表現方法です。
```
****  
****


##### エキスパートAIコース

```
最小二乗法について、テキストを読んでも以下二点がよく分かりませんでしたので、ご回答をお願い致します。
・なぜ2乗しているのか
・なぜ最後に,2で割っているのか
```

## 解答例  

最小２乗法とは「誤差2乗和」が最小となるように超平面（2次元の場合境界線）を決定する方法です。
しかしこの説明だと根本的な解決になっていないので、もう少し数学的な説明を補足します。例えば「2乗していないただの誤差」を考えます。その場合数式で表現すると

<img src="https://latex.codecogs.com/gif.latex?E&space;=&space;\sum_{i=1}^{N}y_{i}-f(x_{i})&space;\nonumber" />

となります。ここでEは誤差関数、y = f(x)は求める境界線、<img src="https://latex.codecogs.com/gif.latex?(x_{i},y_{i})" />は与えられたデータの組みです。なお今回は簡単なため、2変数一次関数を想定しています。  
もちろん、上の誤差<img src="https://latex.codecogs.com/gif.latex?y_{i}-f(x_{i})" />は正負どちらも取り得ます。綺麗に全部の計算結果が>0になることはありません。下の図をみてください。  
<img src="https://user-images.githubusercontent.com/25298659/31658669-a54ae1f2-b36c-11e7-8f93-07e4ec3ae8e3.png">

<img src="https://latex.codecogs.com/gif.latex?(x_{1},y_{1}),(x_{2},y_{2})">の二つのデータがあるとします。
（二乗していない）誤差の定義に従い普通に計算すると、今の場合

<img src="https://latex.codecogs.com/gif.latex?E&space;=&space;(15-8)&space;&plus;&space;(3-10)&space;=&space;0">    

となります。この場合は誤差が0という計算結果になるわけです。果たしてこれでいいのでしょうか？  
このまま計算すると、誤差が0なのでこれが最適な境界線になってしまいます。データ点が離れているのにも関わらずです。
これは上記の「2乗していない誤差」の場合正負による大小を加味していないために起こります。そのため誤差=0という結果になってしまったわけです。もし絶対値記号でもつけて計算しなおせば

<img src="https://latex.codecogs.com/gif.latex?E&space;=&space;(15-8)&space;&plus;&space;|(3-10)|&space;=&space;14">   
　　

となり誤差が存在するので、ここで終了せずにまだまだこの誤差を小さくしようとして計算が進みます。ということでプログラム内で絶対値つければ問題は解決します。

けれど、これをプログラムで実装するときにわざわざif文で場合分けしてコードを長くしなくても済む方法があります。そもそも「場合分け」という作業自体、混乱を招きやすい手法です。（中学時代の関数の場合分けを思い出してみてください。）  
それを解決するために、ここでは「ただの誤差」を「2乗」して全ての結果が>0になるようにしているわけです。そうすれば、場合分けしなくても勝手に全ての計算結果が >0になるので楽です。これが2乗している理由です。ついでに「この2乗することで正負による混乱をなくす」手法は数学の色々なところで用いられている、計算を簡略化するためのテクニックなので、覚えておいてください。  

次に<img src="https://latex.codecogs.com/gif.latex?\frac{1}{2}"> をしている理由です。二つの場合を考えていきましょう。  
・1/2をしている場合  
・1/2をしていない場合  
上述してきた2変数の1次関数の場合でみていきます。Eの最小値を求めるので、「これを偏微分したものが0になる」という方程式を考えればいいということはすでに勉強したと思います。  
求める直線（境界線）が<img src="https://latex.codecogs.com/gif.latex?y=ax&plus;b">の時は

<img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;E}{\partial&space;a}&space;=&space;0,&space;\frac{\partial&space;E}{\partial&space;b}&space;=&space;0">


という二つの連立方程式をとけばいいわけです。

・1/2をしている場合  

<img
src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;\sum_{i=1}^{N}\frac{1}{2}&space;y_{i}-f(x_{i})}{\partial&space;a}&space;=&space;\frac{\partial&space;\sum_{i=1}^{N}\frac{1}{2}y_{i}-f(x_{i})}{\partial&space;a}&space;=&space;\sum_{i=1}^{N}&space;(y_{i}-a-bx_{i})(-1)&space;=&space;0&space;\\&space;\frac{\partial&space;\sum_{i=1}^{N}\frac{1}{2}&space;y_{i}-f(x_{i})}{\partial&space;b}&space;=&space;\frac{\partial&space;\sum_{i=1}^{N}\frac{1}{2}y_{i}-f(x_{i})}{\partial&space;b}&space;=&space;\sum_{i=1}^{N}&space;(y_{i}-a-bx_{i})(-x_{i})&space;=&space;0">



・1/2をしていない場合  
<img
src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;\sum_{i=1}^{N}&space;y_{i}-f(x_{i})}{\partial&space;a}&space;=&space;\frac{\partial&space;\sum_{i=1}^{N}2&space;(y_{i}-f(x_{i}))}{\partial&space;a}\\&space;=&space;\sum_{i=1}^{N}&space;2(y_{i}-a-bx_{i})(-1)&space;=&space;0&space;\\&space;\leftrightarrow&space;\sum_{i=1}^{N}&space;(y_{i}-a-bx_{i})(-1)&space;=&space;0&space;\\&space;\\&space;\frac{\partial&space;\sum_{i=1}^{N}2(y_{i}-f(x_{i}))}{\partial&space;b}&space;=&space;\frac{\partial&space;\sum_{i=1}^{N}2(y_{i}-f(x_{i}))}{\partial&space;b}&space;\\=&space;\sum_{i=1}^{N}2&space;(y_{i}-a-bx_{i})(-x_{i})&space;=&space;0&space;\\&space;\leftrightarrow&space;\sum_{i=1}^{N}&space;(y_{i}-a-bx_{i})(-x_{i})&space;=&space;0">

と結局は1/2をしようがしまいが,最終的に同じ式を計算することには変わりません。  
これは
<img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;E}{\partial&space;a}">や
<img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;E}{\partial&space;b}">自体が大事なのではなく、
<img src="https://latex.codecogs.com/gif.latex?\frac{\partial&space;E}{\partial&space;a}&space;=&space;0,\frac{\partial&space;E}{\partial&space;b}=0">
という方程式がここでは大事だからです。 これが最初の質問でもある「計算簡略化のために2乗する」ということにも繋がっています。重要なのはE自体の式ではなく、Eを最小化するaとbを求めることです。

この微分（偏微分）した後の係数をなくすために先にその係数を1にする（今の場合は2×1/2）という作業は、関数を最適化するラグランジュの未定乗数法を用いた分野では特によく用いられている計算簡略化のためのテクニックです。  
SVM（サポートベクターマシン）やナイーブベイズや誤差逆伝搬学習法でもみられる方法ですので、これも覚えておくとそれらを理解するときにスムーズにいけると思います。
