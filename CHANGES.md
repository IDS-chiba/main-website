# main-website 改修内容まとめ

## 変更点

### 1. 予約システムへのリンクを差し替え
旧: `https://motohirosano.github.io/ids-booking/`
新: `https://ids-chiba.github.io/ids-booking/`

全5ファイルの計13箇所を差し替え済み。

### 2. ロゴをテキスト「IDS」から画像ロゴに差し替え
- ナビゲーション、ヒーロー（トップページ）、フッターの3箇所すべて
- 画像ファイル: `images/ids-logo.png` を読み込み
- 万一PNGが無い場合は `images/ids-logo.svg`（暫定SVG）にフォールバック

★重要: チャットで共有いただいたPNGロゴを、`images/ids-logo.png` というファイル名で `images/` フォルダに保存してください。これだけで正規ロゴが反映されます。

### 3. スタジオ写真を追加
- `images/a-studio/`: A Studio画像6枚（色違いの照明バリエーション）
- `images/b-studio/`: B Studio画像6枚（B→C連結時の写真含む）
- ファイル名は半角英数字にリネーム済み（日本語パス回避）

### 4. レイアウト追加
- **index.html**: ヒーロー直下に「OUR STUDIOS」セクションを追加。A/B各スタジオの代表写真をカード表示。
- **studio.html**: 既存の写真プレースホルダーをミニギャラリーに置き換え（クリックで拡大表示／Lightbox機能付き）。ステージ・連結セクションも写真ギャラリー化。

## GitHubへの反映手順

1. このフォルダの中身をすべて `main-website` リポジトリのローカルクローンにコピー
   - 既存のHTML/CSSは上書きされます
   - `images/` フォルダは新規追加されます
2. PNGロゴ（チャットで共有いただいたもの）を `images/ids-logo.png` として保存
3. git add → commit → push
   ```
   git add .
   git commit -m "feat: ロゴ画像化、写真追加、予約URL更新"
   git push origin main
   ```
4. GitHub Pagesで反映確認

## ファイル構成

```
main-website/
├── index.html      (改修)
├── studio.html     (改修：ギャラリー＋Lightbox)
├── pricing.html    (改修：ロゴ＋URL)
├── member.html     (改修：ロゴ＋URL)
├── contact.html    (改修：ロゴ＋URL)
├── style.css       (改修：ロゴ/ギャラリー/Lightbox用CSS追加)
├── CHANGES.md      (このファイル)
└── images/
    ├── ids-logo.svg          (暫定SVG)
    ├── README-LOGO.txt       (差し替え方法)
    ├── a-studio/             (A Studio写真 6枚)
    └── b-studio/             (B Studio写真 6枚)
```
