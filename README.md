# NGS5th

# Deploy

## 単純なクラスタのデプロイ

- D1_v2(仮想CPUが１つ) の実行ノードが２つと、ヘッドノードが１つ
- D14 の NFSサーバがたちあがります。

NFSサーバのスペックがよいのは、アタッチできるディスクサイズの数が多いためです。
最初から大きなマシンをつくるのであれば、`VM Size` で、指定する仮想マシンのサイズを大きなものにしておく必要があります。

docker と、ジョブスケジューラと、使わないリソースを自動で落とすものが入っています

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmanabuishii%2Fazure-files%2Fmaster%2FNFS_SGE%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

## Galaxy のパイプライン

上記の単純なクラスタに、Galaxy を追加したもの、以下の設定を追加する

Master_script

```
https://raw.githubusercontent.com/manabuishii/azure-files/master/scripts_for_setup/galaxy_SGE/master_script.sh
```
Worker_script

```
https://raw.githubusercontent.com/manabuishii/azure-files/master/scripts_for_setup/galaxy_SGE/exec_script.sh
```

# 注意点

* Azureのアカウントがあるか？
* APIが使えるアカウントか？
* パスワードが期限切れになっていないか？



# 参考

[オープンソース × Azure 活用で、国際競争の激しいゲノム研究に新たな活力を - 国立研究開発法人 理化学研究所 - マイクロソフト導入事例 - Microsoft for Business](https://github.com/manabuishii/NGS5th)
