# Resources/Users

- [TopPage](/api-docs/)

jao Minecraft Server Minecraft サービスにログインしたことのある利用者の情報のみを取得できます。  
1.8.8 鯖(2018/02/17)以前のデータは含まず、1.12.2 鯖(2018/03/20)以降のデータのみを取得可能対象とします。

## Get User

- **GET** `/users`
- **GET** `/users/{minecraft.id}`
- **GET** `/users/{minecraft.uuid}`
- **GET** `/users/{discord.id}`

[ユーザオブジェクト](/api-docs/object/user)を返します。  
この API で返される Minecraft ID は最新でない可能性があることに注意してください。jao Minecraft Server の最終ログインの情報から取得されます。

### Request Parameters

このエンドポイントのパラメータはすべて Optional ですが、いずれかのパラメータがなければなりません。

| Field              | Description                  | Example                                | Remarks |
| :----------------- | :--------------------------- | :------------------------------------- | :------ |
| `{minecraft.uuid}` | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `{discord.id}`     | Discord ID                   | `206692134991036416`                   |         |
| `mcid`             | Minecraft ID                 | `X4Z`                                  |         |
| `uuid`             | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `discordid`        | Discord ID                   | `206692134991036416`                   |         |

### Response

| Field    | Description                                   | Example | Remarks                                                                         |
| :------- | :-------------------------------------------- | :------ | :------------------------------------------------------------------------------ |
| `data`   | [ユーザーオブジェクト](/api-docs/object/user) |         |                                                                                 |
