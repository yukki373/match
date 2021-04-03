# テーブル設計

## users テーブル

| Column                   | Type    | Options                  |
| ------------------------ | ------- | ------------------------ |
| email                    | string  | unique: true null: false |
| encrypted_password       | string  | null: false              |
| name                     | string  | null: false              |
| gender                   | integer | null: false              |
| self_introduction        | text    |                          |