# リポジトリのサプライチェーンを保護しよう

_サプライチェーンを保護し、環境内の依存関係を把握し、それらの依存関係に存在する脆弱性を知り、パッチを適用しましょう。_

## ようこそ

GitHubは、環境内の依存関係の把握から、依存関係に存在する脆弱性の把握とパッチ適用まで、サプライチェーンの保護をサポートします。

- **対象者**: 開発者、DevOpsエンジニア、サイト信頼性エンジニア、セキュリティ専門家
- **学べること**: リポジトリの依存関係の確認、Dependabotアラートの確認、Dependabotによるセキュリティ・バージョンアップデートの有効化方法
- **作成するもの**: リポジトリ依存関係、Dependabotアラート、依存関係修正やバージョンアップデートのプルリクエスト
- **前提条件**: なし
- **所要時間**: この演習は1時間以内で完了できます

この演習では、以下を体験します:

1. 依存関係グラフ
2. 依存関係アラート
3. 依存関係のセキュリティアップデート
4. 依存関係のバージョンアップデート

### 演習の始め方

演習を自分のアカウントにコピーし、お気に入りのOctocat（Mona）に**約20秒**待ってもらい、最初のレッスンが準備できたら**ページをリフレッシュ**してください。

[![](https://img.shields.io/badge/Copy%20Exercise-%E2%86%92-1f883d?style=for-the-badge&logo=github&labelColor=197935)](https://github.com/new?template_owner=yutaka-art&template_name=secure-repository-supply-chain&owner=%40me&name=skills-secure-repository-supply-chain&description=Exercise:+Secure+your+Repository+Supply+Chain&visibility=public)

<details>
<summary>トラブルシューティング 🤷</summary><br/>

演習をコピーする際は、以下の設定を推奨します:

- オーナーには、ご自身の個人アカウントまたは組織を選択してください。

- プライベートリポジトリではActionsの利用分が消費されるため、パブリックリポジトリの作成を推奨します。

20秒経っても演習が準備できない場合は、[Actions](../../actions)タブを確認してください。

- ジョブが実行中か確認してください。少し時間がかかる場合もあります。

- 失敗したジョブが表示された場合は、Issueを提出してください。バグを見つけてくれてありがとう！🐛

</details>

---

&copy; 2025 GitHub &bull; [行動規範](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MITライセンス](https://gh.io/mit)
