# Object/City

- [TopPage](/api-docs/)

jao Minecraft Server Minecraft サービスにおいて運営によって認可され、登録された自治体の情報オブジェクト

| Field         | Type     | Description                    | Example                                                                                                 | Remarks  |
| :------------ | :------- | :----------------------------- | :------------------------------------------------------------------------------------------------------ | :------- |
| `id`          | `int`    | 自治体 ID                      | `1`                                                                                                     |          |
| `name`        | `string` | 自治体名称                     | `爆新地`                                                                                                |          |
| `namekana`    | `string` | 自治体名称読み                 | `ばくしんち`                                                                                            |          |
| `mcid`        | `string` | 自治体管理者プレイヤー名       | `jaotan`                                                                                                |          |
| `uuid`        | `string` | 自治体管理者 UUID              | `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`                                                                  | nullable |
| `discordid`   | `string` | 自治体管理者 Discord ユーザ ID | `222018383556771840`                                                                                    |          |
| `summary`     | `string` | 概要                           | `Jao_Afaワールドの中心に位置する運営が管理する自治体`                                                   | nullable |
| `name_origin` | `string` | 名称の由来                     | `爆発の始まり。爆発の根源。中心地。つまり爆心地。新しいので爆新地。`                                    | nullable |
| `blocknum`    | `int`    | 表面ブロック数                 | `1048576`                                                                                               |          |
| `corners`     | `array`  | 入力範囲情報                   | `[{"id":1,"x":"0","z":"0"},{"id":2,"x":"0","z":"0"},{"id":3,"x":"0","z":"0"},{"id":4,"x":"0","z":"0"}]` |          |
| `reason`      | `string` | 規定ブロックを超える理由       | `null`                                                                                                  | nullable |
| `remarks`     | `string` | 備考                           | `null`                                                                                                  | nullable |
