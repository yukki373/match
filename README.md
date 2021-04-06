# テーブル設計

## users テーブル

| Column                   | Type    | Options                  |
| ------------------------ | ------- | ------------------------ |
| email                    | string  | unique: true null: false |
| encrypted_password       | string  | null: false              |
| name                     | string  | null: false              |
| gender                   | integer | null: false              |
| self_introduction        | text    |                          |
| profile_image            | string  |                          |

### Association

- has_many :reactions

## reactions テーブル

| Column                   | Type       | Options                       |
| ------------------------ | ---------- | ------------------------------|
| from_user_id             | references | null: false foreign_key: true |
| to_user_id               | references | null: false foreign_key: true |
| status                   | integer    | null: false                   |

### Association

- belongs_to :user