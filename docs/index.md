---
layout: default
---

# jao Minecraft Server API Documentation

jao Minecraft Server およびそれに関連するサービスの情報を取得できる API のリファレンスです。  
基本的に外部からこの API が利用されることは想定しておりません。あくまでサービス提供の上で内部的に利用する API ですので、大幅な仕様変更が事前予告なく行われる可能性があります。

API 提供は jao Minecraft Server 開発部が行います。問い合わせは開発部まで。

## Basic Infomation

- BaseURL: `https://api.jaoafa.com/`
- Available Version: `v1` (`https://api.jaoafa.com/v1/`)
- バージョンを指定せずリクエストすることもできます。その場合、最新バージョンが選択されます。
- GET リクエストにおいて、同一エンドポイントに対してのリクエストで同一フィールドを複数指定した場合、`?`で指定されたフィールドを優先して使用します。
  - `v1/users/X4Z?mcid=mine_book000`: mcid=`mine_book000`のデータを取得
  - `v1/users/X4Z?uuid=xxxxx`: uuid=`xxxxx`のデータを取得

### Rate Limits

すべての API において、リクエスト先エンドポイントに関係なく同一 IP アドレスからの 10 秒以内に 2 回以上のリクエストを規制します。  
リクエストが規制された場合、レスポンスヘッダーの`x-ratelimit-reset`に制限が解除される UNIXTime が記載されます。

`/club/token`で取得されたトークンを`usertoken`パラメーターに設定してリクエストした場合、トークンが有効であればレートリミット制限が無効化されます。  
また、Google reCAPTCHAでの認証トークンを`raterecaptcha`パラメーターに設定してリクエストした場合でも、トークンが有効であればレートリミット制限が無効化されます。

### Other Restriction

開発部は開発部の判断により特定 IP からのアクセスを禁止、またはレートリミットを無効化する処置を行うことができます。

## Resources

- [Users](/api-docs_old/resources/users)
- [Cities](/api-docs_old/resources/cities)
- [Club](/api-docs_old/resources/club)

## Object

- [User](/api-docs_old/object/user)
  - [MCBans](/api-docs_old/object/user-mcbans)
  - [MCBans-Ban](/api-docs_old/object/user-mcbans-ban)
- [City](/api-docs_old/object/city)
- [Club-User](/api-docs_old/object/club-user)

## Topics

- [Basic-Response](/api-docs_old/topics/basic-response)
- [Error-Response](/api-docs_old/topics/error-response)
