---
title: Gitチートシート
author: Astro学習者
description: "Gitチートシート"
image:
  url: "https://docs.astro.build/default-og-image.png"
  alt: "惑星と星のイラストの中にastroという単語があります。"
pubDate: 2022-08-08
tags: ["astro", "Git"]
---

## Gitチートシート

### 状態・差分・履歴確認

- 状態の確認（どのファイルが変更されたのか）\
  `git status` \
  簡略化\
   `git status -s` \
   `git status --short`

- 変更してまだステージしていない内容を見るには、引数なし git diff\
  (作業ディレクトリの内容とステージングエリアの内容を比較。追加・削除した行をパッチ形式で表示する)\
  `git diff`

- 次のコミットに含めるべくステージされた内容を知りたい場合\
  （ステージされている変更と直近のコミットの内容を比較）\
  `git diff --staged`\
  `git diff --cached`
- ブランチの差分を比較（ローカルのmainとdev）\
  `git diff main..dev`

- コミット履歴の閲覧\
  `git log`\
  オプション -pで各コミットで反映された変更点を表示（各エントリの直後にそのdiffを表示）\
  `git log -p`\
  オプション -2で直近の2エントリを祝力\
  `git log -p -2`\
  統計情報を見たい場合\
  `git log --stat`\
  デフォルトの書式以外で出力 --pretty オプション：oneline\
  `git log --pretty=oneline`\
  `git log --pretty=short`\
  `git log --pretty=full`\
  `git log --pretty=fuller`\
  フォーマットをカスタマイズできる\
  `git log --pretty=format:"<オプション>"`\
  例）`git log --pretty=format:"%h - %an, %ar : %s"`\
  時間制限のオプション --since --until\
  過去二週間のコミットの一覧を取得\
  `git log --since=2.weeks`\
  `git log --since="2026-10-16"`\
  `git log --since="2 years 1 day 3 minutes ago"`\
  コミット一覧から検索条件にマッチするものだけを取り出す\
  `git log --grep="<検索ワード>"`\
  指定した文字列をコードに追加・削除したコミットのみを表示する\
  `git log --S "<文字列>"`\
  例）`git log -S "class"`
