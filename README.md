# 沼のほとり工房

天体観測まわりの3Dプリント製パーツを製作・紹介するサイト。
天文ファンコミュニティ「[沼のほとり](https://ysmrastro.github.io/numanohotori/)」から派生したブランドです。

- サイトURL: https://ysmrastro.github.io/numa-koubou/
- GitHub Pages + Jekyll（remote theme: Minimal Mistakes / dark skin）

## ローカルプレビュー

```bash
bundle install
bundle exec jekyll serve   # → http://localhost:4000/numa-koubou/
```

## 商品の追加

`_data/products.yml` に1エントリ追加し、画像を `assets/images/products/` に置く。
`status` は `available`（販売中）/ `preparing`（準備中）/ `soldout`（完売）。
販売ページが決まったら `shop_url` に記入すると「購入ページへ」ボタンが表示される。
