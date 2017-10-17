

**該当文**  

```
selfはインスタンスオブジェクト自身を指しています。クラスの中でインスタンスオブジェクトを呼び出す際やそのインスタンスオブジェクトを呼び出す際は、selfを使用します。
```


**修正後**

```
selfはインスタンスオブジェクト自身を指しています。クラスの中でインスタンスオブジェクトを呼び出す際やそのインスタンスオブジェクトを呼び出す際は、selfを使用します。

下の例をみてください。（コードはpythonです。）

class Userinfo:
    def __init__(self,name,birth,address):
        self.name = name
        self.birth = birth
        self.address = address

Einstein = Userinfo("Einstein",1879,"Germany")
print(Einstein.name)
print(Einstein.birth)
print(Einstein.address)


メソッドを定義する際に引数selfを用いて、インスタンスを作成しているのがわかります。このselfがなければインスタンスオブジェクトは作成されないので、インスタンスが持つデータ（今回の例では、nameやbirthやaddress）を操作することができません。selfにはインスタンスを実体化させる働きもあります。そうすると当然,

Einstein = Userinfo("Einstein",1879,"Germany")

と宣言しても、Userinfoの引数が何を表しているのか不明なため、エラーになります。ここでは詳しく述べませんが、selfを理解するにはdef__init__　で表されるメソッド「コンストラクタ」を理解する必要があることに注意してください。


```
