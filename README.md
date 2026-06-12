# ぷにもる サポート / Web 資産

「ぷにもる 〜つゆのおふろそうじ〜」の App Store 提出に必要な Web ページ一式。
`koinobore-support` と同じく GitHub Pages で公開する想定。

## 含まれるもの
- `index.html` … サポートページ(あそびかた / FAQ / 問い合わせ)
- `privacy.html` … プライバシーポリシー(**一般向け+ATT/AdMob** 仕様。こいのぼれの COPPA 版とは別物)
- `app-ads.txt` … AdMob 用の認可ファイル(**設置先はドメイン直下。下記注意**)

## 公開手順(GitHub Pages)
1. このフォルダを `punimoru-support` という名前で **Public** リポジトリにして push(GitHub Pages は無料だと Public のみ。中身は公開前提のページなので機密なし)。
2. GitHub の Settings → Pages → Branch を `main` / `/ (root)` にして有効化。
3. 数分後、`https://kentarokentaro.github.io/punimoru-support/` で公開される。

## App Store Connect に入れる URL
| 欄 | URL |
|---|---|
| サポートURL | `https://kentarokentaro.github.io/punimoru-support/` |
| プライバシーポリシーURL | `https://kentarokentaro.github.io/punimoru-support/privacy.html` |
| マーケティングURL | `https://kentarokentaro.github.io/` ←(**ルート**。app-ads.txt クロール用) |

> マーケティングURLは「オプション」表示だが、**AdMob 使用時は実質必須**。
> Google はここからドメインを取得して `app-ads.txt` をクロールする。

## ⚠️ app-ads.txt の設置場所(重要)
- `app-ads.txt` は **ドメイン直下** に置く必要がある:
  `https://kentarokentaro.github.io/app-ads.txt`
- **この `punimoru-support/` フォルダに置いても無効**(プロジェクトページの配下になるため)。
  ルート用の `kentarokentaro.github.io` リポジトリに置くこと。
- 中身(1行):
  ```
  google.com, pub-2888687215190330, DIRECT, f08c47fec0942fa0
  ```
- **こいのぼれ(koinobori)と同じパブリッシャー `pub-2888687215190330`** なので、
  既に `https://kentarokentaro.github.io/app-ads.txt` がある場合は **その1ファイルで
  ぷにもるも充足**。ブラウザで開いて上記の行があるか確認するだけでよい。
  無ければ、同梱の `app-ads.txt` をルートリポジトリに置く。

## 連絡先
- 開発者: K2 / メール: oikimutida@yahoo.co.jp
