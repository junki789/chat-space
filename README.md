# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|pasword|strung|null: false|
|username|string|null: false|
### Association
- has_many :message
- has_many :group
- belongs_to :groups_users

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|image|text||
|text|text||

### Association
- belongs_to :group
- belongs_to :users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :users

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|

### Association
- belongs_to :users
- has_many :message
- has_many :groups_users