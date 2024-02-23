#テーブル設計
##usersテーブル

| Column             | Type   | Option                    |
|--------------------|--------|---------------------------|
| name               | String | null: false               |
| email              | String | null: false, unique: true |
| encrypted_password | String | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association
- has_many :prototypes
- has_many :comments

###prototypesテーブル
| Column     | Type   | Option      |
|------------|--------|-------------|
| title      | String | null: false |
| catch_copy | text   | null: false |
| concept    | text   | null: false |
| user       | references| null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

##commentsテーブル
| Column    | Type      | Option      |
|-----------|-----------|-------------|
| content   | text      | null: false |
| user      | references| null: false, foreign_key: true |
| prototype | references| null: false, foreign_key: true |

- belongs_to :user
- belongs_to :prototype
