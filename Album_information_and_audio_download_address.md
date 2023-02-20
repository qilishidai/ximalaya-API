## 专辑信息及音频下载地址

### 概述

该API用于获取喜马拉雅FM专辑的音频列表。该API的基本请求地址为：`http://mobwsa.ximalaya.com/mobile/playlist/album/page`。

### 请求

#### 请求URL

- `http://mobwsa.ximalaya.com/mobile/playlist/album/page`

#### 请求方式

- GET

#### 请求参数

| 参数名  | 必选 | 类型   | 说明   |
| ------- | ---- | ------ | ------ |
| albumId | 是   | string | 专辑ID |
| pageId  | 是   | string | 页码   |

#### 请求示例

```
http://mobwsa.ximalaya.com/mobile/playlist/album/page?albumId=74215376&pageId=1
```

### 响应

#### 响应示例

```json
{
    "msg":"0",
    "ret":0,
    "maxPageId":3,
    "pageSize":20,
    "list":[
        {
            "trackId":18738115,
            "trackRecordId":28045195,
            "uid":5503655,
            "playUrl64":"http://aod.cos.tx.xmcdn.com/group18/M04/3B/60/wKgJKlePYUbS63HqABiTtsfb5lY586.mp3",
            "playUrl32":"http://aod.cos.tx.xmcdn.com/group18/M04/3B/A5/wKgJJVePYUCivnTYAAxKAHf5utg456.mp3",
            "playPathHq":"",
            "playPathAacv164":"http://aod.cos.tx.xmcdn.com/group18/M04/3B/A5/wKgJJVePYUPTaubIABjlSzL5uso863.m4a",
            "playPathAacv224":"http://aod.cos.tx.xmcdn.com/group18/M04/3B/A5/wKgJJVePYUGxCr3fAAmHSYXDc6E732.m4a",
            "title":"0 我就要你好好的 预告",
            "duration":201,
            "albumId":4769209,
            "albumTitle":"我就要你好好的/遇见你之前/Me Before You",
            "albumImage":"http://imagev2.xmcdn.com/group17/M00/3B/B1/wKgJKVePZI-CSXNVAAGsLbYEW9M820.jpg!op_type=3&columns=140&rows=140&magick=png",
            "isPaid":false,
            "isFree":false,
            "isVideo":false,
            "isDraft":false,
            "isRichAudio":false,
            "isAuthorized":false,
            "priceTypeId":0,
            "priceTypeEnum":0,
            "type":0,
            "relatedId":0,
            "orderNo":1,
            "vipFirstStatus":0,
            "paidType":0,
            "ximiFirstStatus":0,
            "coverLarge":"http://imagev2.xmcdn.com/group18/M04/3B/60/wKgJKlePYUOQDxJxAAGsLbYEW9M071.jpg!op_type=3&columns=640&rows=640",
            "playtimes":16001
        },
        ...
    ],
    "pageId": 1,
	"totalCount": 53
}
}
```

#### 响应参数

- `pageSize`：每页的数据量，此API中为20。

-   `list`：包含多个音频条目的数组，每个条目表示一个音频。

  - `trackId`：音频ID。
  - `trackRecordId`：音频记录ID。
  - `uid`：用户ID。
  - `playUrl64`：音频的64位播放地址，可以用于下载或在线播放。
  - `playUrl32`：音频的32位播放地址，可以用于下载或在线播放。
  - `playPathHq`：高音质音频播放地址。
  - `playPathAacv164`：低音质aac音频播放地址。
  - `playPathAacv224`：高音质aac音频播放地址。
  - `title`：音频标题。
  - `duration`：音频时长，单位为秒。
  - `albumId`：所属专辑ID。
  - `albumTitle`：所属专辑标题。
  - `albumImage`：所属专辑的图片地址。
  - `isPaid`：是否为付费音频。
  - `isFree`：是否为免费音频。
  - `isVideo`：是否为视频。
  - `isDraft`：是否为草稿。
  - `isRichAudio`：是否为有声书。
  - `isAuthorized`：是否授权。
  - `priceTypeId`：价格类型ID。
  - `priceTypeEnum`：价格类型枚举。
  - `type`：音频类型。
  - `relatedId`：相关ID。
  - `orderNo`：顺序编号。
  - `vipFirstStatus`：VIP状态。
  - `paidType`：付费类型。
  - `ximiFirstStatus`：喜米状态。
  - `coverLarge`：音频封面图片地址。
  - `playtimes`：音频播放次数。
- `pageId`：返表示当前请求返回的是第几页
- `totalCount`：专辑中共有多少个节目



