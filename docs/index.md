---
layout: default
---

# jao Minecraft Server API Documentation


jao Minecraft Serverおよびそれに関連するサービスの情報を取得できるAPIのリファレンスです。  
基本的に外部からこのAPIが利用されることは想定しておりません。あくまでサービス提供の上で内部的に利用するAPIですので、大幅な仕様変更が事前予告なく行われる可能性があります。

API提供はjao Minecraft Server開発部が行います。問い合わせは開発部まで。

## Basic Infomation

- BaseURL: `https://api.jaoafa.com/`
- Available Version: `v1` (`https://api.jaoafa.com/v1/`)

### Rate Limits

すべてのAPIにおいて、リクエスト先エンドポイントに関係なく同一IPアドレスからの10秒以内に2回以上のリクエストを規制します。  
リクエストが規制された場合、レスポンスヘッダーの`x-ratelimit-reset`に制限が解除されるUNIXTimeが記載されます。

### Other Restriction

開発部は開発部の判断により特定IPからのアクセスを禁止、またはレートリミットを無効化する処置を行うことができます。

## Resources

- [Users](/api-docs/resources/users)
- [Cities](/api-docs/resources/cities)

## Object

- [User](/api-docs/object/user)
- [City](/api-docs/object/city)

## Topics

- [Error-Response](/api-docs/topics/error-response)
