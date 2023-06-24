---

layout: ../../layouts/Marklayout.astro
title: '投稿を日付順にソート'
pubDate: 2023-06-24
upDate:
draft: false

---


Astroでサイトを作ると Hugo の用に新しい順に並ばなかったので
下記のページを参考にやってみました。

[Astroで最新記事から日付順に記事一覧を表示する方法/Zenn](https://zenn.dev/miz_dev/articles/astro-sorted-posts)

以下のコードを '''index''' ページに追加したらソートして表示ができました。

```javascript
const sortedPosts = nonDraftPosts.sort((a, b) => {
  const aDate = new Date(a.frontmatter.pubDate);
  const bDate = new Date(b.frontmatter.pubDate);
  return bDate - aDate;
});
```
aaa