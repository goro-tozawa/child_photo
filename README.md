# # users テーブル

|  Column | Type | Options |
| ------------ | ------- | ---------- |
| name      | string | null: false |
| nick_name    | string  | null: false |
| occupation_id | integer | null: false |
| position_id | integer | null: false |
| child_gender | string | null: false |
| child_age | string | null: false |
| child_position_id | integer | null: false |


### Association
- has_many : comments
- has_many : children, through: :comments




## childrenテーブル
|  Column | Type | Options |
| ------------ | ------- | ---------- |
| title      | string | null: false |
| catch_copy | text | null: false |
| concept      | text | null: false |
| image    | ActiveStorage | ------- |
| user | references | null: false  |

### Association
- has_many : comments
- has_many : users, through: :comments


## children_usersテーブル
|  Column | Type | Options |
| ------------ | ------- | ---------- |
| user_id      |  references | null: false |
| children_id   |  references | null: false |

- belongs_to :users
- belongs_to :children


## commentsテーブル

|  Column | Type | Options |
| ------------ | ------- | ---------- |
| text      | text | null: false |
| user_id | references | null: false |
| children_id |  references  | -------- | 

### Association
- belongs_to :users
- belongs_to :children