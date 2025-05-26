## ステップ4: Dependabotバージョンアップデートを有効化して実行しよう

_素晴らしいです！_ :partying_face:

これで、Dependabotが依存関係の脆弱性を自動で検知し、安全なバージョンへのプルリクエストを作成するプロセスが自動化されました！今後はプルリクエストを確認してマージするだけで、依存関係のセキュリティ問題に常に対応できます。

> [!NOTE]  
> Dependabotが複数のプルリクエストを提案していたことに気づきましたか？**axios**依存関係に関するものだけをマージしましたが、他のプルリクエストは**Pull requests**パネルから消えました。これは、axios依存関係のアップグレードによって他の推移的依存関係にも変更が発生し、それらが削除または他のバージョンに更新されたためです。依存関係グラフに変更があると、Dependabotは既存のプルリクエストを自動的に見直し、不要になったものはクローズします。すべてを一度にマージせず、Dependabotに任せましょう！
<img width="955" alt="Screenshot showing that the axios PR was merged and that the 2 others were closed" src="https://github.com/user-attachments/assets/6c97f90b-c6e2-4865-b1eb-dd7053383f07" />

セキュリティアップデート機能はアラート対応を自動化してくれますが、バージョンアップデートへの追従も自動化したいですよね？Dependabotバージョンアップデート機能を使えば、依存関係の新しいバージョンへのプルリクエスト作成も自動化できます。

**Dependabotバージョンアップデートとは？**  
セキュリティアラートだけでなく、Dependabotは依存関係のメンテナンスも自動化できます。リポジトリが依存しているパッケージやアプリケーションの最新リリースに自動で追従できます。セキュリティアラートと同様に、Dependabotは古くなった依存関係を特定し、最新バージョンへのアップデート用プルリクエストを作成します。

実際にやってみましょう！

### :keyboard: アクティビティ 4.1: Dependabotバージョンアップデートを有効化して実行しよう

1. **Settings**（設定）タブに移動し、**Advanced Security**（高度なセキュリティ）を選択します。
1. **Dependabot version updates**（Dependabotバージョンアップデート）を探し、**Configure**（設定）をクリックして新しいファイルエディタを開きます。ファイル名は`dependabot.yml`です。
1. ファイルには、リポジトリ内のGitHub Actions（`github-actions`パッケージエコシステム）のアップデート設定があらかじめ記載されています。
1. `dependabot.yml`の設定ファイルにもう1つエントリを追加し、以下のように編集します。

   ```yaml
   version: 2
   updates:
     - package-ecosystem: "github-actions"
       directory: "/"
       schedule:
         interval: "monthly"
     - package-ecosystem: "nuget"
       directory: "/code/"
       schedule:
         interval: "weekly"
   ```

   > 💡 **ヒント:** github.com上で直接ファイルを編集・コミットできるほか、ピリオドキー（ `.` ）を押すとブラウザで軽量なVS Codeエディタを開けます。

1. 変更を`main`ブランチに直接コミットします。
1. 設定ファイルを更新すると、Monaが進捗を確認し始めます。しばらく待ってコメント欄を確認しましょう。進捗情報や次のレッスンが案内されます。

これでDependabotバージョンアップデートが以下のように動作するようになりました：

- GitHub Actionsのアップデートを月1回チェックし、古いものがあればプルリクエストを作成します。
- .NETパッケージのアップデートを週1回（月曜日）チェックし、古いものがあればプルリクエストを作成します。別の曜日にチェックしたい場合は、[schedule.day](https://docs.github.com/ja/code-security/dependabot/dependabot-version-updates/configuration-options-for-the-dependabot.yml-file#scheduleday)を参照してください。
