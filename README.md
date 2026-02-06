# PIP-BOY 3000 財務管理システム

Fallout風のレトロフューチャーデザインによる、個人用財務管理アプリケーション

![Pip-Boy Style](https://img.shields.io/badge/style-Pip--Boy-green)
![Static Site](https://img.shields.io/badge/hosting-GitHub%20Pages-blue)
![No Backend](https://img.shields.io/badge/backend-none-orange)

## 📋 目次

- [概要](#概要)
- [機能](#機能)
- [デモ](#デモ)
- [セットアップ](#セットアップ)
- [使い方](#使い方)
- [技術スタック](#技術スタック)
- [ファイル構成](#ファイル構成)
- [データ管理](#データ管理)
- [今後の予定](#今後の予定)

## 🎮 概要

Falloutシリーズに登場するPip-Boy 3000をモチーフにした、完全ブラウザベースの財務管理システムです。サーバー不要で動作し、GitHub Pagesで簡単にホスティングできます。

### 特徴

- 🎨 **レトロフューチャーデザイン**: CRTモニター風のエフェクトとスキャンライン
- 💾 **サーバーレス**: 完全にブラウザ内で動作（localStorage使用）
- 🔄 **GitHub Gist同期**: オンラインバックアップ対応（Pip-Boyジャーナル）
- 📊 **本格的な財務三表**: 損益計算書、貸借対照表、キャッシュフロー計算書
- 💳 **クレジットカード管理**: 発生主義による未払金管理
- 📱 **レスポンシブ**: PC・タブレット対応

## ✨ 機能

### Pip-Boyジャーナル (`pipboy-journal.html`)

メインのジャーナルアプリケーション

#### タブ一覧
- **STAT**: ステータス表示（日時・システム情報）
- **JOURNAL**: 日記・ログ記録
  - エントリーの作成・編集・削除
  - Markdown対応
  - GitHub Gist同期
- **TASKS**: タスク管理
  - タスクの追加・完了・編集
  - 完了済みタスクの管理
  - GitHub Gist同期
- **MISSIONS**: ミッション管理
  - ワークフロー形式のミッション
  - ステップごとの進捗管理
  - GitHub Gist同期
- **BUDGET**: 財務管理へのゲートウェイ
  - 財務ダッシュボードへのリンク

### 財務ダッシュボード (`financial-dashboard.html`)

高度な財務管理システム

#### タブ一覧

1. **概要**
   - 今月の純利益
   - 現金残高
   - クレジット未払金
   - 最近の収支（最新10件）

2. **損益計算書 (P/L)**
   - 収入（給与、ボーナス、その他）
   - 支出（8カテゴリ）
   - 純利益計算
   - 3ヶ月比較（先月・今月・来月）
   - グラフ表示（収入vs支出）

3. **貸借対照表 (B/S)**
   - 資産（現金・預金）
   - 負債（クレジット未払金、借入金）
   - 純資産（利益剰余金）
   - 3ヶ月比較
   - グラフ表示（資産・負債・純資産）

4. **キャッシュフロー計算書 (C/F)**
   - 営業活動CF（収入-現金支出）
   - 財務活動CF（借入-返済）
   - 現金増減額
   - 3ヶ月比較
   - グラフ表示

5. **収支入力**
   - 日付、種別（収入/支出）選択
   - カテゴリ別入力
   - クレジットカード支払いオプション
   - メモ機能
   - 入力履歴表示

6. **クレジット管理**
   - 未払い一覧
   - 支払済み一覧
   - 個別支払済み処理
   - 未払金合計表示

7. **財務活動**
   - 借入金管理
   - 返済管理
   - クレジット引落記録

8. **定期支払い**
   - （準備中）

## 🚀 デモ

GitHub Pagesでホスティング可能：

```
https://[ユーザー名].github.io/pipboy-journal/
```

## 📦 セットアップ

### 必要なもの
- GitHubアカウント
- モダンブラウザ（Chrome, Firefox, Safari, Edge）

### インストール手順

1. **リポジトリの作成**
```bash
# 新規リポジトリを作成
mkdir pipboy-journal
cd pipboy-journal
git init
```

2. **ファイルの配置**
```bash
# ダウンロードしたファイルを配置
# - pipboy-journal.html
# - financial-dashboard.html
# - README.md
```

3. **GitHubにプッシュ**
```bash
git add .
git commit -m "Initial commit: Pip-Boy Financial Management System"
git branch -M main
git remote add origin https://github.com/[ユーザー名]/pipboy-journal.git
git push -u origin main
```

4. **GitHub Pagesの有効化**
   - リポジトリの Settings > Pages
   - Source: `main` ブランチを選択
   - Save

5. **アクセス**
   - `https://[ユーザー名].github.io/pipboy-journal/pipboy-journal.html`

### ファイル名の変更（オプション）

より簡潔なURLにするには：

```bash
# pipboy-journal.html を index.html にリネーム
mv pipboy-journal.html index.html
git add .
git commit -m "Rename to index.html"
git push
```

これで `https://[ユーザー名].github.io/pipboy-journal/` でアクセス可能になります。

## 📖 使い方

### 基本的なワークフロー

#### 1. 日常の収支管理

**Pip-Boyジャーナル起動**
1. ブラウザでアプリを開く
2. `BUDGET` タブをクリック
3. `OPEN FINANCIAL DASHBOARD` をクリック

**収支を記録**
1. 財務ダッシュボードで `収支入力` タブ
2. 日付と金額を入力
3. 種別（収入/支出）を選択
4. カテゴリを選択
5. クレジット支払いの場合はチェック
6. `追加` をクリック

#### 2. クレジットカード管理

**買い物時（クレジット支払い）**
```
収支入力 タブ
→ 支出を選択
→ カテゴリ: 食費
→ ✅ クレジットカード支払い
→ 追加
```

**引き落とし確認**
```
クレジット管理 タブ
→ 未払い一覧で確認
→ 支払済みボタンをクリック
→ 支払済み一覧に移動
```

#### 3. 財務三表の確認

**損益計算書**
- 今月の収支状況を確認
- 先月・今月・来月の比較
- カテゴリ別の支出傾向を分析

**貸借対照表**
- 現在の資産状況を確認
- 負債（クレジット未払金、借入金）をチェック
- 純資産の推移を確認

**キャッシュフロー**
- 現金の動きを確認
- 営業活動と財務活動を分析
- 月次の現金増減をチェック

### GitHub Gist同期（Pip-Boyジャーナルのみ）

**初回設定**
1. GitHub Personal Access Tokenを取得
   - https://github.com/settings/tokens
   - `gist` スコープのみ選択
2. Pip-Boyジャーナルの設定画面で入力
3. 保存するとGistが自動作成される

**同期タイミング**
- データ保存時に自動同期
- 手動同期も可能

## 🛠 技術スタック

### フロントエンド
- **HTML5**: 構造
- **CSS3**: スタイリング（Fallout Pip-Boy風デザイン）
- **Vanilla JavaScript**: ロジック（フレームワーク不使用）

### データ管理
- **localStorage**: ブラウザ内永続化
- **GitHub Gist API**: オンラインバックアップ（オプション）

### ホスティング
- **GitHub Pages**: 静的サイトホスティング（無料）

### 特徴的な技術

**CRTエフェクト**
```css
/* スキャンライン */
animation: scanline 8s linear infinite;

/* ビネット効果 */
background: radial-gradient(ellipse at center, transparent 0%, rgba(0, 0, 0, 0.7) 100%);
```

**発生主義会計**
- クレジット支払い時に費用計上
- 未払金として負債計上
- 引き落とし時に未払金減少

## 📁 ファイル構成

```
pipboy-journal/
├── README.md                    # このファイル
├── pipboy-journal.html          # メインジャーナルアプリ
└── financial-dashboard.html     # 財務ダッシュボード
```

### ファイルサイズ
- `pipboy-journal.html`: 約80KB（すべてのロジック込み）
- `financial-dashboard.html`: 約50KB（財務計算ロジック込み）

## 💾 データ管理

### localStorage構造

#### Pip-Boyジャーナル
```javascript
{
  "journalEntries": [],      // 日記エントリー
  "tasks": [],               // タスクリスト
  "missions": [],            // ミッション
  "transactions": []         // 旧予算データ（非推奨）
}
```

#### 財務ダッシュボード
```javascript
{
  "financialEntries": [      // 収支データ
    {
      "date": "2026-02-06",
      "type": "expense",
      "category": "食費",
      "amount": 3000,
      "memo": "ランチ",
      "isCredit": true,
      "creditPaid": false,
      "timestamp": 1738800000000
    }
  ],
  "financeEntries": [        // 財務活動データ
    {
      "date": "2026-02-01",
      "type": "借入",
      "amount": 100000,
      "memo": "住宅ローン",
      "timestamp": 1738300000000
    }
  ]
}
```

### データのバックアップ

**方法1: ブラウザ開発者ツール**
```javascript
// localStorageの全データをエクスポート
console.log(JSON.stringify(localStorage));

// 特定データのバックアップ
localStorage.getItem('financialEntries');
```

**方法2: GitHub Gist同期**
- Pip-Boyジャーナルは自動同期対応
- 財務ダッシュボードは未対応（今後追加予定）

### データのリストア

```javascript
// localStorageにインポート
localStorage.setItem('financialEntries', '[バックアップデータ]');
```

## 🎨 カスタマイズ

### 色の変更

メインカラーは `#22c55e`（Pip-Boy緑）です。変更する場合：

```css
/* 検索: #22c55e */
/* 置換: #yourcolor */
```

### カテゴリの追加

支出カテゴリを追加する場合：

1. HTML内の `<optgroup label="支出">` に追加
2. データ集計ロジックに追加（renderPL関数など）

### 財務諸表の期間変更

現在は「先月・今月・来月」の3ヶ月表示です。期間を変更する場合：

```javascript
// renderPL関数内
const months = [
    new Date(now.getFullYear(), now.getMonth() - 2, 1), // 2ヶ月前
    new Date(now.getFullYear(), now.getMonth() - 1, 1), // 先月
    now.toISOString().slice(0, 7),                      // 今月
];
```

## 🐛 トラブルシューティング

### データが表示されない

**原因**: localStorageが無効
**解決**: ブラウザの設定でlocalStorageを有効化

### GitHub Gist同期が失敗する

**原因**: トークンの権限不足
**解決**: `gist` スコープを持つトークンを再発行

### グラフが表示されない

**原因**: データが0件
**解決**: 収支データを入力してから確認

### クレジット未払金が減らない

**原因**: 「支払済み」ボタンを押していない
**解決**: クレジット管理画面で個別に「支払済み」を設定

## 📋 今後の予定

### 短期（v1.1）
- [ ] 定期支払い機能の完全実装
- [ ] 財務ダッシュボードのGitHub Gist同期
- [ ] データエクスポート機能（CSV/JSON）
- [ ] カテゴリのカスタマイズ機能

### 中期（v1.2）
- [ ] グラフの拡充（月次推移、年次推移）
- [ ] 予算設定機能
- [ ] カテゴリ別予算 vs 実績
- [ ] 支出アラート機能

### 長期（v2.0）
- [ ] 複数通貨対応
- [ ] 投資管理機能
- [ ] レポート自動生成
- [ ] モバイルアプリ化（PWA）

## 🤝 コントリビューション

現在は個人プロジェクトですが、改善提案やバグ報告は歓迎します。

### バグ報告
GitHubのIssuesで報告してください：
- 現象の説明
- 再現手順
- 使用ブラウザとバージョン
- スクリーンショット（可能であれば）

### 機能リクエスト
GitHubのIssuesで「Feature Request」として投稿してください。

## 📄 ライセンス

MIT License

## 👤 作者

Pip-Boy 3000 財務管理システム

## 🙏 謝辞

- デザインインスピレーション: Fallout シリーズ（Bethesda Softworks）
- このプロジェクトはファンメイドであり、Bethesda Softworksとは関係ありません

## 📞 サポート

質問や問題がある場合：
1. このREADMEを確認
2. GitHubのIssuesを検索
3. 新しいIssueを作成

---

**VAULT-TEC APPROVED | RADIATION LEVEL: SAFE | SYSTEM STATUS: OPERATIONAL**
