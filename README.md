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
- has_many :chat_room_users
- has_many :chat_rooms, through: :chat_room_users

## reactions テーブル

| Column                   | Type       | Options                       |
| ------------------------ | ---------- | ------------------------------|
| from_user_id             | references | null: false foreign_key: true |
| to_user_id               | references | null: false foreign_key: true |
| status                   | integer    | null: false                   |

### Association

- belongs_to :user

## chat_room_users テーブル

| Column                   | Type       | Options                       |
| ------------------------ | ---------- | ------------------------------|
| chat_room_id             | references | null: false foreign_key: true |
| user_id                  | references | null: false foreign_key: true |

### Association

- belongs_to :user
- belongs_to :chat_room

## chat_rooms テーブル

| Column                   | Type       | Options                       |
| ------------------------ | ---------- | ------------------------------|
|                          | references | null: false foreign_key: true |

### Association

- mas_many :chat_room_users
