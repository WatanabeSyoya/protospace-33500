# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| name       | string | null: false |
| email      | string | null: false |
| password   | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments
 


## prototypes テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | string     | null: false |
| concept    | string     | null: false |
| user       | references |             |

### Association

- has_many :comments
- belongs_to :user


## comments テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | string     | null: false |
| user      | references | references  |
| prototype | references | references  |

### Association

- belongs_to :user
- belongs_to :prototype

