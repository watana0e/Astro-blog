---
layout: ../../layouts/Marklayout.astro
title: 'Astroの下書き'
tag: ['Astroの使い方' , 'Frontmatter',]
pubDate: 2023-06-21
upDate: 2023-06-21 23:18
draft: false
---
<!-- コメントアウト -->

## 下書き

``` `posts/*.md` ``` 下のMarkdownファイルに下書き（表示されない）状態にするには  
Frontmatter に ``` `draft:[status]` ```と書く  
``` `[status]` ```に以下を書くとindexページ反映される  
- true
  - 表示されない
- false
  - 表示される

---

## indexページに表示されないようにする
下書き状態にしてもindexページに表示されてしまう。  
表示されないようにするには

```javascript
const posts = await Astro.glob('../pages/posts/*.md');
const nonDraftPosts = posts.filter((post) => !post.frontmatter.draft);
```

を ``` `index.astro` ``` の Frontmatter に追加する。
``` `nonDraftPosts` ``` で ``` `.map~以下略~` ``` コードを書く
