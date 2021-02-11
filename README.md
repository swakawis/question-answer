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

# Question-Answer DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false, index: true|
### Association
- has_many :questions
- has_many :answers

## questionsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|content|text|null: false|
|user_id|string|null: false, foreign_key: true|
### Association
- has_many :answers
- belongs_to :user

## Answersテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|string|null: false, foreign_key: true|
|question_id|string|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :question