---
description: GitHub専用レポジトリのworkフォルダにパワーポイントと画像をアップロードして，CHiBi-CHiLO登録データを入手してください．
---

# 1A．CHiBi-CHiLO登録データの入手（Wowza）

{% hint style="warning" %}
以下の手順は，CHiBi-CHiLOで利用しているストリーミングサーバーが**Wowza**である場合のものになります．

利用しているストリーミングサーバーがVimeoである場合は，[1B．CHiBi-CHiLO登録データの入手（Vimeo）](convert-vimeo.md)をご参照ください．不明な場合は，担当者にご確認ください．
{% endhint %}

### （1）GitHub専用レポジトリにアクセス

[GitHubアカウントの準備](../prepare/github.md#2repojitorihenoakusesu)で招待された専用レポジトリにアクセスして下さい．

### （2）workフォルダに移動

専用レポジトリで，workフォルダ→担当者から指定されたフォルダに移動します．

![](<../.gitbook/assets/image (21).png>)

### （3）データアップロード

❶ 自分のフォルダに[STEP1](../narration/save-powerpoint.md)で保存した以下のデータを**同時に選択し，**ドラッグ＆ドロップします．

* パワーポイント（ファイル名は半角英数字）&#x20;
* スライドの画像（パワーポイントファイル名と同名のフォルダにまとめて）

![](<../.gitbook/assets/image (296).png>)

❷ アップロードされたファイルの一覧が表示されるので，すべてのファイルがアップロードされたことを確認して**「Commit changes」**をクリックします．

![](<../.gitbook/assets/image (209).png>)



### （4）データ変換の確認

❶ データをアップロードしたら**「Actions」**タブをクリックします．

![](<../.gitbook/assets/image (315).png>)

❷ All workflowsの一覧にアップロードしたユーザーの名前で，**「Add files via upload」**と表示されているのを確認します．

❸**「Add files via upload」**をクリックすると変換状況を確認できます．

![](<../.gitbook/assets/image (385).png>)

### （5）CHiBi-CHiLO登録データのダウンロード

❶ **changes**と**generate**のアイコンが共に緑になると変換が完了です．&#x20;

{% hint style="info" %}
アイコンが緑にならない，あるいは**Artifacts**にアイコンが表示されない場合は以下をご確認下さい．
{% endhint %}

{% content-ref url="fail-conversion.md" %}
[fail-conversion.md](fail-conversion.md)
{% endcontent-ref %}

❷ **Artifacts**に表示されているアイコンをクリックすると，**CHiBi-CHiLO登録データ**をZipファイルでダウンロードできます．登録方法は[STEP3：CHiBi-CHiLOに登録](broken-reference)をご確認ください．

![](<../.gitbook/assets/image (120).png>)

{% hint style="info" %}
CHiBi-CHiLO登録データの保存期間は1日です．消えてしまっている場合は，右上の**「Re-run all jobs」**をクリックすると再度生成されます．
{% endhint %}

{% hint style="info" %}
macOSのSafariで，Zipファイルが自動的に展開され，動画ファイルやjsonファイルが表示される場合は，以下を参考に設定をご変更ください．

[ Q. GitHubからダウンロードしたZipファイルが自動的に展開されてしまう](../other/faq.md#q-githubkaradaunrdoshitazipfairuganisareteshimau)
{% endhint %}

### （6）登録データ内の合成音声ビデオの確認

❶ **Zipファイル**を展開すると，スライド毎の合成音声ビデオファイル（MP4）が入っています．ビデオを再生して変換の結果が確認できます．&#x20;

❷ 必要に応じてパワーポイントを修正し，再度アップロードを行って下さい．**パワーポイントの差し替え方法**は，[\[参考\]GitHubのファイル操作 パワーポイントの差し替え](github.md#pawpointonoshie)をご確認下さい．

