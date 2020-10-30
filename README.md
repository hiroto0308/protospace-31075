# テーブル設計

## users テーブル

| column     | type   | options  |
| ---------- | ------ | -------- |
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association 

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| column     | type             | options  |
| ---------- | ---------------- | -------- |
| title      | string           | NOT NULL |
| catch_copy | text             | NOT NULL |
| concept    | text             | NOT NULL |
| image      | ActiveStorage    |          |
| user       | references       |          |

### Association 

- belongs_to :user
- has_many :comments

## comments テーブル

| column    | type       | options  |
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

### Association 

- belongs_to :prototypes
- belongs_to :users