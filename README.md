## 

## usersテーブル

|column|type|options|
|------|----|-------|
user_id|integer|null: false, foreign_key: true|
name|ｓｔring|null: false|
email|ｓｔring|null: false, add_index : users, :email, unique: true|
pass|ｓｔring|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :messages


### groupsテーブル
|Column|Type|Options|
|------|----|-------|
group_name|ｓｔring|null: false|
group_id|integer|null: false, foreign_key: true|

### Association
- has_many :users, through: :groups_users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
text|string||
img|string||
group_id|integer|null: false, foreign_key: true|
user_id|integer|null: false, foreign_key: true|

### Association
- belong_to :users
- belong_to :groups

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :groups
- belongs_to :users