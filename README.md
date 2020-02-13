## 

## userテーブル

|column|type|options|
|------|----|-------|
user_id|integer|null: false, foreign_key: true|
name|ｓｔring|null: false|
email|ｓｔring|null: false, add_index : users, :email, unique: true|
pass|ｓｔring|null: false|

### Association
- has_many :groups_users
- has_many :message


### groupテーブル
|Column|Type|Options|
|------|----|-------|
group_name|ｓｔring|null: false|
group_id|integer|null: false, foreign_key: true|

### Association
- has_many :groups_users
- has_many :message

## messageテーブル
|Column|Type|Options|
|------|----|-------|
text|string||
img|string||
group_id|integer|null: false, foreign_key: true|
user_id|integer|null: false, foreign_key: true|

### Association
- belong_to :user
- belong_to :group

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user