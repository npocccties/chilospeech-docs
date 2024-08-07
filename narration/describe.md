---
description: パワーポイントのナレーション原稿を記述します．
---

# 1．ナレーション原稿の記述

## 準備

❶ 音声合成ビデオにするパワーポイントを開きます．

{% hint style="info" %}
Web版パワーポイントの場合は，あらかじめデスクトップ版パワーポイントで作成したファイルをOneDriveにドラッグ＆ドロップでアップロードしてから開いて下さい．

* アカウントをお持ちの方はから<img src="../.gitbook/assets/image (390).png" alt="" data-size="line">[**こちら**](https://www.office.com/launch/powerpoint?auth=2)からOneDriveアクセスできます．
{% endhint %}

❷ パワーポイントのメニューの **「ホーム」→「CHiLO-Speech」** をクリックし．アドインを表示します．

アドインを登録していない場合は，以下を確認してアドインを登録して下さい．

{% content-ref url="../prepare/powerpoint-1.md" %}
[powerpoint-1.md](../prepare/powerpoint-1.md)
{% endcontent-ref %}

![](<../.gitbook/assets/image (243).png>)

❸ パワーポイントのメニューの **「表示」→「ノート」** で，ノート部を表示します．

![](<../.gitbook/assets/image (240).png>)

## ナレーション原稿の記述

各スライドのノート部にナレーション原稿を記載すると，合成音声でスライドを解説する合成音声ビデオ教材を作成することができます．

ビデオ教材はスライド毎にビデオが分割されており，分割されたビデオを **「トピック」** ，ビデオ教材全体を **「ブック」** と呼びます．

ナレーション原稿は **（1）設定項目** ， **（2）ナレーションスクリプト** ， **（3）解説** で構成されています． それぞれ以下の内容を記述します．

**（1）設定項目：** トピックのタイトルや話者の種類など，トピックの設定を行います．

**（2）ナレーションスクリプト：** 合成音声で読み上げるスクリプトを記述します．

**（3）解説：** トピックに表示される解説文を記述します．​​

![](<../.gitbook/assets/image (310).png>)

### （1）「設定項目」の記載

設定項目では作成するトピックの設定を指定します．記述は以下の形式で行います．

```
設定項目名:設定値
```

トピック設定項目は全部で13種類ありますが，トピックタイトルを指定する **「Topic:」のみが必須項目** となっています．

{% hint style="danger" %}
**「Topic:」** を設定していないスライドがあると，CHiBi-CHiLOに登録する際にエラーが発生する場合があります．
{% endhint %}

また，よく利用する設定項目として **「Voice:」** があります．voiceは合成音声の話者を指定する項目で， **「Takumi」を指定すると男性声，「Kazuha」や「Tomoko」を指定すると女性声** の合成音声が出力されます．

```
Topic:VUCA時代に求められている学び
Voice:Takumi
```

#### アニメーション動画の作成

連続するスライドの **「Topic:」** に同じトピックタイトルを指定すると，複数のスライドを1つのトピック（動画）にまとめる事ができます． 少しづつ変化するスライドを作成し，同じトピックタイトルを指定するとアニメーションしているような動画を作成することができますので，是非チャレンジしてみて下さい．

![](<../.gitbook/assets/image (403).png>)

その他の設定項目については、以下を参照してください．

{% content-ref url="text.md" %}
[text.md](text.md)
{% endcontent-ref %}

### （2）「ナレーションスクリプト」の記載

合成音声で読み上げるスクリプトを， バッククォートと呼ばれる **「\`」** を使って` ```text〜``` ` で囲んで作成します．

#### -音声合成の調整

単語の読み方や強調，間の調整は，SSMLタグやSpeechMarkdownを使って行います．

````
```text
このような(ブーカ時代)[kana:"ブーカジ'ダイ"] に豊かな人生を送り，社会を持続的に発展させるには，
[break:"1s"]学びの成果が活かせること[break:"1s"]，
すべての (人々)[ruby:"ひ'とびと"] に教育の機会が提供されること[break:"1s"]，
そして生涯にわたり学び続けることが求められております．[break:"1s"]
われわれはこのような学びを提供する学習システムの開発を目指しています.
```
````

SSMLタグやSpeechMarkdownの詳細は以下を参照してください．

{% content-ref url="text.md" %}
[text.md](text.md)
{% endcontent-ref %}

#### -よく使うタグのコピー

音声合成で使用する頻度の高いタグをCHiLO-Speechの作業ウインドウに設定しています．オレンジ色のボタンをクリックすると空のタグがコピーされるので，例やマニュアルを参考に必要な箇所にペーストして使用します．

* 「break」（間を開ける）
* 「ruby」（読み方を設定する）
* 「kana」（読み方とイントネーションを設定する）

![](<../.gitbook/assets/image (14).png>)

#### -音声合成の確認

音声の確認をするスクリプトを選択し，アドインの **「音声の確認」** をクリックすると音声合成を確認できます．（音声が再生されます）

![](<../.gitbook/assets/image (2) (1).png>)

### （3）「解説」の記載

トピックに表示する解説文を， **「\`」** を使って` ```description ``` ` で囲んで記載します．

````
```description
学びの成果が活かせること
すべての人々に教育の機会が提供されること
生涯にわたり学び続けること
```
````

トピックに解説を記載しない場合は `description` に何も記載せず，次のように記述して下さい．

````
```description
```
````

解説はGitHub Flavored Markdownに対応しています．

箇条書きの場合，以下のように行頭に`-`を追加します．

````
```description
- 学びの成果が活かせること
- すべての人々に教育の機会が提供されること
- 生涯にわたり学び続けること
```
````

その他の記法は以下を参照してください．

* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)（外部サイトに移動）
