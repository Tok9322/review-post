# ReviewPost — Google Stitch 用プロンプト

以下をStitchに貼り付けてください。

---

## プロンプト（日本語版）

```
飲食店の来店客が、食後に感想カードを作成・シェアできるモバイルWebアプリを作ってください。

## アプリ名
ReviewPost（レビューポスト）

## アプリの目的
飲食店の来店客が食後にQRコードからアクセスし、自分の料理写真と簡単な感想をもとに、おしゃれな「感想カード」画像を自動生成する。来店客が自分のSNSに投稿したくなるデザイン品質が最重要。

## 画面構成（4画面）

### 画面1: ウェルカム画面
- 店舗ロゴと店舗名を上部に表示（例：「炭火居酒屋 たなか」）
- 「ごちそうさまを、1枚に。」というキャッチコピー
- 「カードをつくる」ボタン（大きく、目立つデザイン）
- 背景は温かみのある暗めのトーン（飲食店の雰囲気に合う）

### 画面2: 感想入力画面
3つのステップ形式で、1問ずつ表示（スワイプまたはNextボタンで進む）

**Step 1「今日のベストは？」**
- メニュー名をタップで選択（チップUI、横スクロール）
- 例: 🍖牛タン塩 / 🍣刺身盛り / 🍺レモンサワー / 🥗シーザーサラダ
- 「その他」で自由入力も可能

**Step 2「今日の気分は？」**
- 大きな絵文字を3つ並べてタップ選択
- 😍 最高！ / 😊 満足！ / 😋 また来る！

**Step 3「写真を選ぶ（任意）」**
- 「📷 料理の写真を選ぶ」ボタン（端末のカメラロールから選択）
- スキップも可能（写真なしでもカード生成OK）

**Step 4「ひとこと（任意）」**
- 短いテキスト入力欄（プレースホルダー：「例：牛タンが柔らかくて最高！」）
- スキップ可能

### 画面3: カード生成・プレビュー画面
- 生成された感想カードを画面中央に大きく表示
- カードのデザイン要素：
  - ユーザーの料理写真（選択した場合）が背景またはメインビジュアル
  - AIが生成したおしゃれな感想コピー（例：「とろける幸せ、ここにあり。」）
  - 店舗名とロゴ（小さめ、さりげなく）
  - 日付
  - 選択した気分の絵文字
- カード下部に操作ボタン：
  - 「🔄 デザインを変える」— タップで別デザインパターンに切り替え
  - 「📱 保存する」— 端末のカメラロールに画像保存
  - 「シェアする」— OS標準の共有シートを起動（X, Instagram, LINE等）
- その下に控えめなリンク：
  - 「📍 Googleマップで口コミを書く」（タップでGoogleマップの口コミ画面へ遷移）

### 画面4: サンクス画面
- 「ありがとうございました！」のメッセージ
- クーポン表示エリア（店舗が設定している場合のみ表示）
  - 例：「次回ドリンク1杯サービス🎁」
  - クーポンコードまたはQR表示
- 「もう1枚つくる」ボタン（別の料理でもう一度カード作成）

## デザイン要件
- モバイルファースト（スマートフォン縦画面に最適化）
- ダークモード基調（飲食店の雰囲気に合う、料理写真が映える）
- カードデザインは高品質でSNS投稿したくなるレベル
- フォントは日本語対応（Noto Sans JP等）
- アニメーション：カード生成時にふわっと表示されるトランジション
- ボタンは大きめでタップしやすい（指で操作前提）

## カードデザインのバリエーション（🔄で切り替え）
- スタイルA：写真を大きく配置、下部にコピーとロゴ（Instagram風）
- スタイルB：写真に半透明のオーバーレイ、中央にコピー（シネマティック風）
- スタイルC：写真を丸くクロップ、周囲にテクスチャ背景（雑誌風）

## 技術的な注意
- ログイン不要。来店客の個人情報は一切保存しない
- 写真はブラウザ内で処理し、サーバーに保存しない
- カード画像の生成はクライアントサイド（Canvas API / html2canvas）
- レスポンシブではなくモバイル専用でOK（QRコードからのアクセス前提）

## デモ用のダミーデータ
- 店舗名：「炭火居酒屋 たなか」
- メニュー候補：牛タン塩、刺身盛り合わせ、レモンサワー、シーザーサラダ、焼き鳥盛り
- AIコピーの例：「炭火の香りに包まれた、至福のひととき。」
```

---

## プロンプト（英語版・おすすめ）

Stitchは英語プロンプトの方が精度が高い傾向があるため、こちらを推奨。
**アプリのUI・テキストは全て日本語で出力されるよう指示済み。**

```
Create a mobile web app called "ReviewPost" for Japanese restaurant customers to create and share beautiful review cards after dining.

IMPORTANT: All UI text, labels, buttons, placeholders, and generated content must be in Japanese. The app's target users are Japanese-speaking customers.

## Purpose
After dining, customers scan a QR code, answer 3 quick questions, optionally add their food photo, and get a beautifully designed "review card" image they'll want to share on social media.

## Screen Flow (4 screens)

### Screen 1: Welcome
- Restaurant logo and name at top (demo: "炭火居酒屋 たなか")
- Tagline: "ごちそうさまを、1枚に。"
- Large CTA button: "カードをつくる"
- Dark, warm background tone (restaurant ambiance)

### Screen 2: Input (step-by-step, one question per view with swipe or Next button)

Step 1 — "今日のベストは？"
- Horizontal scrollable chips: 🍖牛タン塩 / 🍣刺身盛り / 🍺レモンサワー / 🥗シーザーサラダ / 🍗焼き鳥盛り
- "その他" chip opens free text input

Step 2 — "今日の気分は？"
- 3 large emoji buttons:
  - 😍 最高！
  - 😊 満足！
  - 😋 また来る！

Step 3 — "写真を選ぶ（任意）"
- "📷 料理の写真を選ぶ" button (opens device photo picker)
- "スキップ" link below

Step 4 — "ひとこと（任意）"
- Short text input, placeholder: "例：牛タンが柔らかくて最高でした！"
- "スキップ" link below

### Screen 3: Card Preview
- Generated review card displayed large and centered
- Card elements:
  - User's food photo as background or main visual (if provided)
  - AI-generated stylish Japanese caption (demo: "炭火の香りに包まれた、至福のひととき。")
  - Restaurant name and logo (subtle, bottom corner)
  - Date (e.g., 2026.4.4)
  - Selected mood emoji
- Action buttons below the card:
  - "🔄 デザインを変える" — cycles through 3 card styles
  - "📱 保存する" — saves card image to device
  - "シェアする" — triggers OS native share sheet (X, Instagram, LINE, etc.)
- Subtle secondary link below buttons:
  - "📍 Googleマップで口コミを書く"

### Screen 4: Thank You
- Message: "ありがとうございました！"
- Coupon area (conditional display, only shown if restaurant has set one):
  - Example: "次回ドリンク1杯サービス 🎁"
  - Coupon code or QR display
- "もう1枚つくる" button

## Card Design Variations (cycle with 🔄 button)
- Style A: Large photo layout, caption and logo at bottom (Instagram-style)
- Style B: Photo with semi-transparent dark overlay, centered caption (cinematic)
- Style C: Circular photo crop, textured warm background (magazine editorial style)

All card styles must render Japanese text beautifully.

## Design Requirements
- Mobile-first (portrait smartphone only, no desktop layout needed)
- Dark mode base (warm dark tones — makes food photos pop)
- Card visual quality is the #1 priority — must be beautiful enough to share on SNS
- Japanese font: Noto Sans JP (headings can use a display weight)
- Smooth fade-in animation when card appears on Screen 3
- Large, finger-friendly tap targets (minimum 48px)
- Color palette: warm amber/orange accents on dark background

## Technical Notes
- No login required. Zero personal data collection or storage.
- Photos processed client-side only (Canvas API / html2canvas), never uploaded
- Mobile-only layout (accessed via QR code at the restaurant)
- All text content in Japanese

## Demo Data
- Restaurant name: 炭火居酒屋 たなか
- Menu items: 牛タン塩、刺身盛り合わせ、レモンサワー、シーザーサラダ、焼き鳥盛り
- AI caption examples:
  - "炭火の香りに包まれた、至福のひととき。"
  - "この一皿に、笑顔がこぼれる。"
  - "また会いに来たくなる、あの味。"
```
