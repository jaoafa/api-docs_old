----
layout: default
----

# Users

jao Minecraft Server Minecraftサービスにログインしたことのある利用者の情報のみを取得できます。  
1.8.8鯖(2018/02/17)以前のデータは含まず、1.12.2鯖(2018/03/20)以降のデータのみを取得可能対象とします。

## Get User

**GET** `/users`

[ユーザオブジェクト](/object/user)を返します。

### Request Parameters

このエンドポイントのパラメータはすべてOptionalですが、いずれかのパラメータがなければなりません。

|Field|Description|Example|Remarks|
|:-|:-|:-|:-|
|name|[optional] Minecraft ID|X4Z||
|uuid|[optional] Minecraft UUID (with hyphen)|5799296a-d1ec-4252-93bd-440bb9caa65c||
|discordid|[optional] Discord ID|206692134991036416||

## Response

|Field|Description|Example|Remarks|
|:-|:-|:-|:-|
|status|Request status (boolean)|true|falseの場合、[エラーレスポンス](/topics/error-response)が使用されます|
|data|[ユーザーオブジェクト](/object/user)|||
