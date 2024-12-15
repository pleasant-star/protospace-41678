# テーブル設定

## usersテーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column  | Type       | Options     |
| ------- | ---------- | ----------- |
| title   | string     | null: false |
| catch   | text       | null: false |
| concept | text       | null: false |
| user    | references | null: false |

### Association

- belongs_to :user
- has_many :comments

## commentsテーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| content   | text       | null: false |
| prototype | references | null: false |
| user      | references | null: false |

### Association

- belong_to :user
- belong_to :prototype