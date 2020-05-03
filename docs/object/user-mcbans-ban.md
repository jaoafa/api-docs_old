# Object/User-MCBans

- [TopPage](/api-docs/)

MCBans ユーザデータオブジェクト

| Field        | Type        | Description                  | Example                                | Remarks |
| :----------- | :---------- | :--------------------------- | :------------------------------------- | :------ |
| `uuid`       | `string`    | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `reputation` | `double`    | MCBans user reputation       | `10`                                   |         |
| `global`     | `int`       | Number of Global Ban         | `0`                                    |         |
| `global_ids` | `array`     | Global BanIDs                | `[]`                                   |         |
| `local`      | `int`       | Number of Local Ban          | `0`                                    |         |
| `local_ids`  | `array`     | Local BanIDs                 | `[]`                                   |         |
| `updated_at` | `timestamp` | Data update datetime (JST)   | `2020-04-01 00:00:00`                  |         |
