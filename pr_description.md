# Add memo application database schema

## 概要
個人メモアプリのデータベーススキーマをridgepoleで定義しました。

## 変更内容
- `Schemafile`を作成してデータベーススキーマを定義
- 4つのテーブルを実装:
  - `users`テーブル（ユーザー管理）
  - `memos`テーブル（メモ本体）
  - `memo_tags`テーブル（タグ管理）
  - `memo_taggings`テーブル（メモ-タグ関連付け）

## テーブル設計詳細

### usersテーブル
- `name`: ユーザー名（必須）
- `birthdate`: 生年月日
- `gender`: 性別（string型）

### memosテーブル
- `title`: メモタイトル
- `content`: メモ内容
- `author_id`: 作成者ID
- `posted_at`: 投稿日時

### memo_tagsテーブル
- `name`: タグ名（ユニーク）

### memo_taggingsテーブル
- `memo_id`: メモID
- `memo_tag_id`: タグID

## 設計方針
- FK制約なし（アプリケーションレベルで管理）
- 適切なインデックス設定
- 将来の拡張性を考慮した命名規則

## Link to Devin run
https://app.devin.ai/sessions/944aaa8413b1489aadc02e897d73421d

## Requested by
Ninomiya Jun (jun.ninomiya@gmail.com)
