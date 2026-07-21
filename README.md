# Koki Fujisawa

## [dotfiles](https://github.com/melumuccu/dotfiles)

#### 概要

- chezmoi ベース dotfiles (Mac / Linux / WSL 共通)
- シークレット誤公開防止
  - gitleaks - pre-commit / pre-push (他 repo でも標準採用)
  - Bitwarden CLI

#### 解消したペイン

- 複数端末の設定同期が面倒
  - -> push/pull の簡単なコマンドで実現

## [ai](https://github.com/melumuccu/ai)

#### 概要

- AI Agent 向け skill 集約 repo
- この repo を [skills](https://github.com/vercel-labs/skills) で指定することでグローバル skills を一括導入可
- 外部 skill と自作 skill の二層構成
  - 自作 skill = `kf-g-*` の命名規則
- skills.json 自動生成でクラウド Agent も web 経由で skills 参照可能

#### 解消したペイン

- skills を知人に共有したり、どんな skills を使っているかを伝えにくい
  - -> repo を教えるだけにできた
- 各グローバル skills をどこから引っ張ってきたか忘れる (新PCセットアップ時など)
  - -> この repo にグローバル skills を集約し、この repo から全て取得するだけで良くなった

## [immich](https://github.com/melumuccu/immich)

#### 概要

- [Immich](https://immich.app/) を土台に、画像のスコアリング検索・不要画像一括削除・バックアップを自前ツールで回す個人運用リポジトリ。
  - 例として "screenshot" でスコアリング検索 -> スクショが高スコアになるので、スコア閾値を指定して閾値以上の画像を一括削除

#### 解消したペイン

- Google Photo 、うっかり息子の ╰⋃╯ がUPされようものなら垢BAN対象！？
  - -> Immich で脱 Google Photo
- 自宅サーバだけに画像があると消失が怖い
  - -> Backblaze B2 に自動バックアップ (基本参照しない前提なので、置く場所だけと考えると料金お安め)
- 長期で残す意味のない画像の整理が時間かかる
  - -> スコアリング検索 + 閾値以上一括削除 で一気に消せるようにした

## [line-alive-check-bot](https://github.com/melumuccu/line-alive-check-bot)

#### 概要

- 独居家族の安否確認をLINEで安否確認するBot
- UX: ボタン1タップ回答
- 未返信 -> Slack通知
- Docker Compose分離構成。
- API・scheduler・Tunnel を分離したCompose構成

#### 解消したペイン

- 既存の類似サービスは「1日何回 / 何時に 安否確認が飛ぶか」「どのくらい安否確認を放置したら親族に連絡がいくか」が柔軟に変えられない
  - -> 全て解消。柔軟に設定し、母子2人暮らしの姉用に運用中。

## [nicorepo](https://github.com/melumuccu/nicorepo)

#### 概要

- ニコニコ動画のフォロー新着を Playwright で定期収集し SQLite 保存し、SvelteKit GUI で閲覧する個人アーカイブ

#### 解消したペイン

- 本家のフォロー新着ページは公開から1ヶ月経った動画は見れなくなる -> 忙しい時期は見逃しが多発する
  - -> SQLite に保存されるから時間が経っても流れない
- さまざまな端末で動画を見ているとどこまで見たかわからなくなる ( <a> タグのテキストは閲覧済みで色が変わるのが通例だが、別端末で閲覧済みかどうかは判定されなかったりする)
  - -> 未視聴/視聴済み を SQLite で管理しているので複数端末対応！
- 本家のフォロー新着ページにはフォローしている投稿者の動画であるものの、興味ない動画も多々流れる
  - -> 「投稿者名 x 動画タイトル (部分一致)」 で一括スキップ可能にして解消

