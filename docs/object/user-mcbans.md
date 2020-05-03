# Object/User-MCBans-Ban

- [TopPage](/api-docs/)

MCBans Ban データオブジェクト

| Field        | Type        | Description                               | Example               | Remarks |
| :----------- | :---------- | :---------------------------------------- | :-------------------- | :------ |
| `mcid`       | `string`    | Minecraft ID                              | `X4Z`                 |         |
| `banned_by`  | `string`    | Minecraft ID of the user who executed Ban | `Console`             |         |
| `reason`     | `string`    | Ban reason                                | `griefing`            |         |
| `server`     | `string`    | Server on which Ban was run               | `play.jaoafa.com`     |         |
| `type`       | `string`    | Ban type                                  | `global`              |         |
| `lostrep`    | `double`    | Number of lost reputation                 | `3`                   |         |
| `date`       | `timestamp` | Ban datetime (JST)                        | `2020-04-01 00:00:00` |         |
| `updated_at` | `timestamp` | Data update datetime (JST)                | `2020-04-01 00:00:00` |         |
