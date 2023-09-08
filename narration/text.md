---
description: 音声合成の設定やCHiBi-CHiLOの設定を変更する場合は，以下のようにテキストを作成してください．
---

# \[参考] 音声合成用テキストの仕様

## ■ 設定項目一覧

CHiBi-CHiLOで使用する音声合成では以下の設定ができます．記述は`設定項目名:設定値`の形式で行います．

継続利用がtrueとなっている設定項目についてはノートに設定を記載したスライド以降のページにも設定が適用されます．

### - 音声合成ビデオの書き出し設定

| 設定項目名      | 説明                                                       | 初期値    | 設定値記入例           | 継続利用 |
| ---------- | -------------------------------------------------------- | ------ | ---------------- | ---- |
| Delay      | 先頭の無音区間(秒,浮動少数）                                          | 1.0    | Delay:1.25       | true |
| Pad        | 末尾の無音区間(秒,浮動小数)                                          | 1.0    | Pad:1.25         | true |
| Fade       | フェードイン・フェードアウトの時間(秒,浮動小数)                                | 0      | Fade:1.0         | true |
| Voice      | <p>合成音声の話者の指定。<br>Takumiは男性声、KazuhaまたはTomokoは女性声となる。</p> | Takumi | Voice:Kazuha     | true |
| SampleRate | 音声のサンプリングレートを指定                                          | 22050  | SampleRate:44100 | true |

### - CHiBi-CHiLOの教材設定

| 設定項目名     | 説明                                                | 初期値  | 設定値記入例                        | 継続利用  |
| --------- | ------------------------------------------------- | ---- | ----------------------------- | ----- |
| Topic（必須） | トピックのタイトル                                         | (なし) | Topic:VUCA時代に求められている学び        | false |
| Language  | 言語。指定しなかった場合は、jaとなる。                              | ja   | Language:en                   | true  |
| CreatedAt | <p>作成日時。<br>指定しなかった場合は、PowerPointの作成日時が適用される。</p> | (なし) | CreatedAt:2015-02-16T00:00:00 | true  |
| UpdatedAt | <p>更新日時<br>指定しなかった場合は、PowerPointの更新日時が適用される。</p>  | (なし) | UpdatedAt:2015-02-16T00:00:00 | true  |

## ■ ナレーションスクリプト

合成音声の調整にはSSMLタグとSpeech Markdownに対応しています．

* [サポートされている SSML タグ - Amazon Polly](https://docs.aws.amazon.com/ja\_jp/polly/latest/dg/supportedtags.html)（外部サイトに移動）
* [What Is Speech Markdown? | Speech Markdown](https://www.speechmarkdown.org/basics/what/)（外部サイトに移動）

以下、よく使うタグを紹介します．

### - 無音区間（息継ぎ）

スクリプトエリアのテキストで無音区間（息継ぎ）を追加したい部分に、以下のタグを挿入します．

{% hint style="info" %}
ビデオの先頭と末尾に無音区間を追加したい場合は[設定項目一覧](text.md#she-ding-xiang-mu-yi-lan)のDelayとPadがおすすめです．
{% endhint %}

#### SSML

```
既存のLMSをカスタマイズすることなく<break time="0.2s"/>容易に追加機能として提供することができます．
既存のLMSをカスタマイズすることなく<break time="1s"/>容易に追加機能として提供することができます．
```

#### Speech Markdown

```
既存のLMSをカスタマイズすることなく[break:"0.2s"]容易に追加機能として提供することができます．
既存のLMSをカスタマイズすることなく[break:"1s"]容易に追加機能として提供することができます．
```

### - 読み

単語の読みは以下のいずれかの方法で指定します．\
※ テキストの中にSSMLとSpeech Markdownの両方のタグが混在していても問題ありません．

#### SSML

```
<phoneme type="ruby" ph="にっぽんばし">日本橋</phoneme>
<phoneme type="ruby" ph="かれし">彼氏</phoneme>
```

#### Speech Markdown

```
(日本橋)[ruby:"にっぽんばし"] 
(彼氏)[ruby:"かれし"] 
```

### - アクセント

単語のアクセントの位置を変える場合は，以下のいずれかの方法で，アクセントの箇所に半角のアポストロフィを追加します（最大1箇所まで）．

#### SSML

```
<phoneme alphabet="x-amazon-pron-kana" ph="ニッポ'ンバシ">日本橋</phoneme>
<phoneme alphabet="x-amazon-pron-kana" ph="カ'レシ">彼氏</phoneme>
```

#### Speech Markdown

```
(日本橋)[kana:"ニッポ'ンバシ"] 
(彼氏)[kana:"カ'レシ"] 
```

複数の箇所にアクセントを入れたい場合は，単語を半角スペースで区切るか，別々のタグで囲んでください．

#### SSML

```
<phoneme alphabet="x-amazon-pron-kana" ph="バ'ス ガスバ'クハツ">バスガス爆発</phoneme>．
<phoneme alphabet="x-amazon-pron-kana" ph="バ'ス">バス</phoneme><phoneme alphabet="x-amazon-pron-kana" ph="ガスバ'クハツ">ガス爆発</phoneme>．
```

#### Speech Markdown

```
(バスガス爆発)[kana:"バ'ス ガスバ'クハツ"]．
(バス)[kana:"バ'ス"](ガス爆発)[kana:"ガスバ'クハツ"]．
```

### -話す速度

単語などの話す速度を調整したい場合は，以下のように，速度を指定します．\
速度は，遅い順から `x-slow`,`slow`,`medium`,`fast`,`x-fast` を指定できます．

#### SSML

```
<prosody rate="slow">日本橋</prosody> 
```

#### Speech Markdown

```
(日本橋)[rate:"slow"] 
```

### -指定の組み合わせ

SSMLで読み，アクセントと話す速度の指定を組み合わせる場合は，以下のようにSSMLタグを入れ子構造にします．

```
<prosody rate="slow">
 <phoneme alphabet="x-amazon-pron-kana" ph="ニッポ'ンバシ">日本橋</phoneme>
</prosody>
```

{% hint style="warning" %}
読みまたはアクセント→話す速度の順番でタグを入れると，エラーが発生します．

上記のように，話す速度→読みまたはアクセントの順番で記載タグを入れてください．
{% endhint %}

Speech Markdownの場合は以下のように`;`で区切って指定します．こちらは，アクセント→話す速度の順番で指定しても問題ありません．

```
(日本橋)[rate:"slow";kana:"ニッポ'ンバシ"]
```
