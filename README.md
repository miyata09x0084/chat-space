## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false, unique: true, index: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups,  through:  :groups_users



## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|name|index|unique: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :users,  through:  :groups_users



## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|content|string||
|image|string||
|group|references|foreign_key: true|
|user|references|foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## group_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group|references|foreign_key: true|
|user|references|foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


