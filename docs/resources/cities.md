# Cities

jao Minecraft Server Minecraftサービスにおいて運営によって認可され、登録された自治体の情報を取得・編集できます。

## Get City

**GET** `/cities`

[自治体オブジェクト](/api-docs/object/city)を返します。

### Request Parameters

このエンドポイントのパラメータはすべてOptionalですが、いずれかのパラメータがなければなりません。

|Field|Description|Example|Remarks|
|:-|:-|:-|:-|
|id|自治体ID|1||
|name|自治体名|爆新地||

### Response

|Field|Description|Example|Remarks|
|:-|:-|:-|:-|
|status|Request status (boolean)|true|falseの場合、[エラーレスポンス](/api-docs/topics/error-response)が使用されます|
|data|[自治体オブジェクト](/api-docs/object/city)|||

## Create City (Request)

新規自治体登録のリクエストをします。

**POST** `/cities/create`

## Approval City Request

**POST** `/cities/approval`

自治体のリクエストを承認し、反映します。

## Reject City Request

**POST** `/cities/reject`

自治体のリクエストを否認します。

## Update City Data

**PUT** `/cities`

自治体情報を更新します。
