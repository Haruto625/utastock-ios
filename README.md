# うたストック iOS開発スターター

既存のWebアプリを元にした、Windowsで開発を始めるためのプロジェクトです。初期曲データは空です。

## Windowsでの準備
1. Node.js LTS と VS Code をインストール
2. このZIPを展開し、VS Codeでフォルダを開く
3. ターミナルで `npm install`
4. `npm run dev` でブラウザテスト（ViteのURLを開く）

Web画面の編集先は `www/index.html` です。保存後、ブラウザを更新してください。

## iOSビルド（Macまたは対応するmacOSクラウド環境が必要）
1. Apple Developer Programに登録
2. `capacitor.config.json` の `appId` を自分の固有のBundle IDに変更（`jp.example.utastock` は仮値）
3. `npm install` → `npx cap add ios` → `npx cap sync ios`
4. `npx cap open ios` でXcodeを開き、Signing & CapabilitiesのTeamを設定
5. 実機テスト → Archive → App Store Connect → TestFlight → 審査提出

## 注意
- 保存はlocalStorage。アプリ削除でデータが消える可能性があるため、JSONバックアップを用意しています。iOS上のファイル書き出し・読み込み動作は実機確認が必要です。
- iOS用の署名済みアプリはこのZIPには含まれません。
- 課金機能、クラウド同期、プライバシーポリシー、ストア用画像は未実装です。
- Webサイトを包んだだけでは審査に通る保証はありません。ネイティブの使い勝手や機能追加が必要です。
- CapacitorとNodeの対応バージョンを導入時に公式ドキュメントで確認してください。
