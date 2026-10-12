# 利用者情報変更・確認：アイコンセット

ご指定の画像（青から青緑へのグラデーション、白い利用者カード、右下の更新マーク）から、**同じ原本を一度だけ使用**してすべてのサイズを作成しています。

## ファイル一覧

| ファイル | 内容 |
| --- | --- |
| icon-master.png | 元画像そのまま（1254 × 1254） |
| favicon-16x16.png | ブラウザタブ等（16 × 16） |
| favicon-32x32.png | ブラウザタブ等（32 × 32） |
| favicon-48x48.png | 高解像度favicon（48 × 48） |
| favicon.ico | 16 / 32 / 48ピクセルを内包するICO |
| apple-touch-icon.png | iPhone / iPad用（180 × 180） |
| icon-152.png | Apple端末など向け（152 × 152） |
| icon-167.png | Apple端末など向け（167 × 167） |
| icon-180.png | Apple端末など向け（180 × 180） |
| icon-192.png | Android / PWA向け（192 × 192） |
| icon-512.png | Android / PWA向け（512 × 512） |
| site.webmanifest | PWA用のmanifest（通常の静的サイト向け） |
| html-head-snippet.txt | 通常のHTMLのheadへ追加するタグ例 |
| examples/index.html | 静的プレビュー用の**サンプル** |
| examples/install.html | インストール案内の**サンプル** |

## 通常のWebサイトでの導入

1. PNG / ICO / webmanifestをサイトの公開フォルダに配置します。
2. `html-head-snippet.txt`のタグをHTMLの`<head>`へ追加します。
3. 別フォルダに置く場合は `href` と `site.webmanifest` 内のパスを変更します。
4. HTTPSで配信し、ブラウザのキャッシュを必要に応じて更新します。

## Google Apps Script (GAS) の場合の重要事項

GASのHTMLServiceは、通常の静的Webサイトのように `./icon-192.png` 等のPNGをプロジェクトへ配置して、そのパスから直接配信する構造ではありません。したがって、GASの既存Webアプリでは**上記タグをそのまま貼り付けても画像が表示されない場合があります**。HTTPSでアクセスできる適切な画像配信先と実際のGAS実装に合わせたURL設定が必要です。機微な利用者データはアイコン画像や公開URLには含めないでください。

`examples/index.html` と `examples/install.html` はプレビューの例です。**既存アプリの `Index.html` や `install.html` を上書きしないでください。**

## 制作について

- 元画像を加工・再生成して別デザインにせず、同じ画像からリサイズしています。
- 16pxなど極小サイズでは、文字を模した細い線はつぶれる場合があります。
- PWAのmanifestの`start_url`、`scope`、アプリ名は実際の配置構成に合わせて調整してください。
- アイコン自体を未承認の外部サービスへ公開する必要はありません。公開URLの扱いは施設の方針に従ってください。
