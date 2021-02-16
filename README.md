# テーブル設計

## usersテーブル

| Column             | Type    | Options                   |
| ------------------ | ------- | ------------------------- |
| email              | string  | null: false unique: true  |
| encrypted_password | string  | null: false               |
| nickname           | string  | null: false               |
| task               | integer | null: false               |

### Association

has_many :schedules
has_many :comments

## scheduleテーブル

| Column | Type       | Options     |
| ------ | ---------- | ----------- |
| task_c | text       | null: false |
| order  | string     | null: false |
| user   | references |             |


### Association

belongs_to :user
has_many   :comments

## commentテーブル

| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| text     | text       | null: false |
| user     | references |             |
| schedule | references |             |


### Association

belongs_to :user
belongs_to :schedule