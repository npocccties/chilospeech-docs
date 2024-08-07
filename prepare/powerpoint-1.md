---
description: CHiLO-Speechアドインを登録すると，実際の人工音声を聞きながらパワーポイントにナレーションスクリプトを記述することができます．
---

# 2．パワーポイントへのアドイン登録

パワーポイントの種類について

CHiLO-Speechアドインは，以下のパワーポイントに登録することができます．

{% hint style="info" %}
* Web版パワーポイント（Office on the web）
* デスクトップ版パワーポイント（Microsoft office2016以上）
{% endhint %}

Web版パワーポイントとは，Webブラウザで利用することができるパワーポイントです．Office on the webにユーザー登録して無料で利用できるほか，Office365のアカウントでも利用することができます．

Web版パワーポイントはデスクトップ版と比較し，アドインを簡単に登録することができます．ただし，デスクトップ版に比べて機能が限定されています．また，パソコンに保存されたパワーポイントファイルを直接編集できないため，ファイルを一旦，OneDriveやSharePointにアップロードしてから，編集しなければいけません．

従って，デスクトップ版パワーポイントでスライドを作成し，ナレーションスクリプトを追加する時だけ，Web版パワーポイントを利用することをお勧めいたします．

* アカウントをお持ちの方はから<img src="../.gitbook/assets/image (390).png" alt="" data-size="line">[**こちら**](https://www.office.com/launch/powerpoint?auth=2)からOneDriveアクセスできます．

## CHiLO-Speechアドインの登録方法

### （1）マニフェストファイルの取得

マニフェストファイル（manifest.xml）とは，アドインをパワーポイントに登録するために必要なファイルです． マニフェストファイルは利用機関により異なっています．

大阪教育大学の方は，以下URLからmanifestファイルを開き，

* 右クリック→名前を付けて保存（Chrome，Edgeの場合）
* 右クリック→ページを別名で保存（Safariの場合）

で保存してください。

{% file src="../.gitbook/assets/manifest_oku.xml" %}

### （2）マニフェストファイルの保存

パソコンの任意の場所に **「manifest」** と言う名前のフォルダを作成し，そこに取得したマニフェストファイル（manifest.xml）を保存します．

**以降の設定方法はWeb版，デスクトップ版，OSによって異なります．**

{% tabs %}
{% tab title="Web版の場合" %}
**【Web版の場合】**

**（3）パワーポイントの設定**

❶ OneDriveにアクセスし，パワーポイントを開きます．

* アカウントをお持ちの方はから<img src="../.gitbook/assets/image (390).png" alt="" data-size="line">[**こちら**](https://www.office.com/launch/powerpoint?auth=2)からOneDriveアクセスできます．

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

❷ パワーポイントメニューの **「ホーム」→「アドイン」** を選択します． **「アドイン」** のメニューが表示されない場合は，メニュー右下の<img src="../.gitbook/assets/image (306).png" alt="" data-size="line">マークをクリックしてリボンを表示して下さい．

❸ **「個人アドイン」** メニューで **「アドインのアップロード」** をクリックします．

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

❹ **「参照」** をクリックして，保存したマニフェストファイルを選択し， **「アップロード」** をクリックします．

❺ ホームに追加される **「CHiLO-Speech」** をクリックすると， アドインが表示されます．

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="デスクトップ版・Windows の場合" %}
**【デスクトップ版・Windows の場合】**

**（3）マニフェストファイルの設定**

❶ 作成したmanifestフォルダを右クリックしてプルダウンメニューを表示し， **「プロパティ(R)」** 選択します．

❷ プロパティダイアログボックスの **「共有」** タブを選択し， **「共有(s)...」** をクリックします．

![](<../.gitbook/assets/image (197).png>)

❸ **「共有する相手を選んでください」** というダイアログボックスが現れるので，自分のユーザー名が選択されていることを確認し， **「共有(H)」** をクリックします．

❹ **「すべてのパブリックネットワークにネットワークの探索とファイル共有を有効にしますか？」** というダイアログボックスが現れるので， **「いいえ、接続しているネットワークをプライベートネットワークにします」** をクリックします．

![](<../.gitbook/assets/image (56).png>)

❺「終了」をクリックします．

❻ 「共有」タブに戻るので，ネットワークパスの¥マーク二つから始まるアドレス部分（例：¥¥DESKTOP¥Users¥ties-staffxx¥document¥manifest）をコピーします．（2-3 ❹で使用します．）

❼「閉じる」をクリックしてプロパティダイアログボックスを閉じます．

![](<../.gitbook/assets/image (195).png>)

**（4）パワーポイントの設定**

❶ パワーポイントを起動します．

❷ パワーポイントのメニューの **「ファイル」→「オプション」→「トラストセンター」→「トラストセンターの設定(T)...」** を開きます．

![](<../.gitbook/assets/image (173).png>)

❸ トラストセンターのメニューで **「信頼できるアドインカタログ」** を選択します．

❹ カタログのURLに（2−1）でコピーしたをアドレスをペーストして， **「カタログの追加(A)」** をクリックします．

❺ 追加したアドレスがテーブルに表示されたことを確認し **「メニューに表示する」** にチェックを入れ、 **「OK」** をクリックします．

![](<../.gitbook/assets/image (226).png>)

❻ パワーポイントを再起動します．

❼ パワーポイントが再起動したら，パワーポイントのメニューの **「開発」→「アドイン」** を選択します． **「アドイン」** のメニューが表示されない場合は，メニュー右下の<img src="../.gitbook/assets/image (306).png" alt="" data-size="line">マークをクリックしてリボンを表示して下さい．

❽ Officeアドインダイアログボックス **「共有フォルダー」** タブを選択し， **「CHiLO-Speech」** を選択して **「追加」** をクリックします．

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

❾ **「CHiLO-Speech」** をクリックすると， アドインが表示されます．

![](<../.gitbook/assets/image (397).png>)
{% endtab %}

{% tab title="デスクトップ版・macOS の場合" %}
**【デスクトップ版・macOS の場合】**

**（3）フォルダ作成**

❶ DockのLanchpadから **「ターミナル」** と検索してターミナルを開きます．

![](<../.gitbook/assets/image (349).png>)

❷ ターミナルに以下のコマンドをコピー＆ペーストして **「wef」** フォルダを作成します．

```
mkdir ${HOME}/Library/Containers/com.microsoft.Powerpoint/Data/Documents/wef
```

❸ ターミナルに以下のコマンドをコピー＆ペーストして，作成した **「wef」** フォルダを開きます．

```
open ${HOME}/Library/Containers/com.microsoft.Powerpoint/Data/Documents/wef
```

**（4）マニフェストファイルの移動**

Finderで開いたフォルダに取得したマニフェストファイルを移動します．

![](<../.gitbook/assets/image (396).png>)

**（5）アドインの設定**

❶ パワーポイントを起動します．

❷ パワーポイントメニューの **「挿入」** をクリックします．

❸ 個人用アドインの右側にある **「下矢印」** をクリックします．

❹ 表示されるプルダウンメニューから， **「CHiLO-Speech」** をクリックします.

![](<../.gitbook/assets/image (309).png>)

❺ アドインが追加表示されます．

![](<../.gitbook/assets/image (246).png>)
{% endtab %}
{% endtabs %}
