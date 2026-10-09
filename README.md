# Everyday Bloom v1.1

習慣管理PWA。HTML / CSS / JavaScript、IndexedDBによる端末内保存。通知やクラウド同期はありません。

## 利用開始

GitHub PagesのHTTPS URLにアクセスして利用します。スマートフォンではブラウザの「ホーム画面に追加」を選択してください。初回アクセス時にアプリ一式がキャッシュされ、その後オフラインでも利用できます。

## GitHub Pages

1. GitHubで `everyday-bloom` というPublicリポジトリを新規作成。
2. ZIPを解凍し、`index.html` などのファイルと アイコン画像を**リポジトリ直下**にアップロード。
3. `Commit changes` をクリックし、コミット先を `main` に設定。
4. `Settings` → `Pages` → `Build and deployment` → `Deploy from a branch` → `main` / `(root)` → `Save`。
5. 数分後、`https://ユーザー名.github.io/everyday-bloom/` にアクセス。反映されない場合はPagesの公開URLとActionsの状況を確認。

**コミットメッセージ:** `Initial release Everyday Bloom v1.1`

## データとバックアップ

記録はブラウザのIndexedDBに保存され、スマホとPC間では自動同期されません。設定画面からJSONバックアップを保存してください。復元はデータを置き換えます。ブラウザデータを消すと記録が失われる可能性があります。

## 仕様上の注意

- 週は日曜〜土曜。
- 数値・タイマー記録は目標未達でも途中経過を保存できます。
- タイマーは記録画面を開いている間に計測し、「計測分を追加」→「記録を保存」で確定します。画面を閉じると未保存の計測時間は失われます。
- 週回数型の連続記録は週単位、毎日・曜日指定型は予定実施日単位で算定します。
- 過去の目標設定履歴は保存されます。目標変更は当日以降の判定に適用します。
- オフラインで更新版を公開した場合、Service Workerキャッシュ名を更新してください。

## v1.1 変更点
- アイコン2枚をindex.htmlと同じ階層に配置。manifest、HTML、Service Workerの参照を更新。
- ホームに週回数型の進捗を明示。
- PWAキャッシュを更新し、オンライン時は最新ファイルを優先。
- 既存IndexedDB名とデータ形式を維持。更新前にJSONバックアップを推奨。
