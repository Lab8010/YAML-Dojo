# YAML-Dojo

Kubernetes Manifest、OpenShift Manifest、Ansible Playbookを題材に、YAMLを楽しく学ぶための静的クイズWebアプリです。

- 日本語／英語切替（選択はブラウザに保存）
- 初級・中級・上級の3段階
- 正解数とポイントをブラウザに保存
- 依存関係やビルド処理なしでGitHub Pagesに公開可能

100問へ拡張する際の構成は [QUESTION_BANK_PLAN.md](QUESTION_BANK_PLAN.md) を参照してください。

## GitHub Pagesで公開する

1. このディレクトリをGitHubのリモートリポジトリにpushします。
2. GitHubの **Settings → Pages** で **Deploy from a branch** を選びます。
3. `main` ブランチ、`/(root)` を選択して保存します。

ビルドやサーバーは不要です。`index.html`をブラウザで開けばローカルでも確認できます。
