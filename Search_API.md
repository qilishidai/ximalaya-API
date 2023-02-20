# 喜马拉雅搜索API

## API概述

喜马拉雅搜索API提供了对喜马拉雅音频内容的搜索功能。用户可以通过指定关键词、搜索范围等条件来查询符合要求的音频。

## API请求

- 请求URL：https://www.ximalaya.com/revision/search
- 请求方法：GET
- 请求参数：

| 参数名       | 类型   | 是否必填 | 说明                                   |
| ------------ | ------ | -------- | -------------------------------------- |
| core         | 字符串 | 是       | 搜索的资源类型。album-专辑，track-声音 |
| kw           | 字符串 | 是       | 搜索的关键词                           |
| page         | 整数   | 否       | 搜索结果的页数，每页20个               |
| spellchecker | 布尔值 | 否       | 是否开启拼写纠错                       |
| rows         | 整数   | 否       | 每页的结果数量，默认20                 |
| condition    | 字符串 | 否       | 搜索条件。relation-相关度，time-最新   |
| device       | 字符串 | 否       | 设备类型。iPhone、android、pc、web等   |
| fq           | 字符串 | 否       | 过滤器，根据某个字段的值进行过滤       |

- 请求示例：[https://www.ximalaya.com/revision/search?core=album&kw=%E7%BC%96%E7%A8%8B&page=1&spellchecker=true&rows=20&condition=relation&device=iPhone](https://www.ximalaya.com/revision/search?core=album&kw=编程&page=1&spellchecker=true&rows=20&condition=relation&device=iPhone)

## API响应

- 响应数据格式：JSON
- 响应参数：

| 参数名                    | 类型   | 说明                                            |
| ------------------------- | ------ | ----------------------------------------------- |
| ret                       | 整数   | 响应结果码。200表示请求成功，其他值表示请求失败 |
| msg                       | 字符串 | 响应结果描述信息                                |
| data.result.response.docs | array  | 搜索结果。每个元素表示一个搜索结果              |
| play                      | 整数   | 播放次数                                        |
| user_source               | 字符串 | 用户来源                                        |
| cover_path                | 字符串 | 封面图片URL                                     |
| title                     | 字符串 | 标题                                            |
| uid                       | 整数   | 用户ID                                          |
| url                       | 字符串 | 详情页链接                                      |
| pinyin                    | 字符串 | 标题的拼音                                      |
| category_id               | 整数   | 分类ID                                          |
| intro                     | 字符串 | 简介                                            |
| id                        | 整数   | ID                                              |
| is_paid                   | 布尔值 | 是否付费                                        |
| is_finished               | 整数   | 专辑状态。1表示已完结，0表示未完结              |
| tags                      | 字符串 | 标签                                            |
| category_title            | 字符串 | 分类标题                                        |
| isDraft                   | 布尔值 | 是否为草稿                                      |
| created_at                | 整数   | 创建时间                                        |
| type                      | 字符串 | 资源类型。1表示专辑，2表示声音                  |
| last_uptrack_at_hour      | 整数   | 最后一次更新的时间戳                            |
| is_v                      | 布尔值 | 是否为认证用户                                  |
| refund_support_type       | 整数   | 退款支持类型                                    |
| count_comment             | 整数   | 评论数                                          |
| score                     | 浮点数 | 评分                                            |
| price_type_id             | 整数   | 价格类型ID                                      |
| updated_at                | 整数   | 更新时间                                        |
| isVipFree                 | 布尔值 | 是否为VIP免费                                   |
| nickname                  | 字符串 | 用户昵称                                        |
| custom_title              | 字符串 | 用户自定义标题                                  |
| verify_type               | 整数   | 用户认证类型                                    |
| vipFreeType               | 整数   | 搜索结果中专辑VIP免费类型                       |
| serialState               | 整数   | 搜索结果中专辑是否为连载中的状态                |
| price_type_enum           | 整数   | 搜索结果中专辑价格类型的枚举值                  |
| tracks                    | 整数   | 搜索结果中专辑的集数                            |
| isNoCopyright             | 布尔型 | 搜索结果中专辑是否为无版权内容                  |
| comments_count            | 整数   | 搜索结果中专辑的评论数量                        |
| price_types               | 数组   | 搜索结果中专辑的价格类型                        |
| anchorUrl                 | 字符串 | 搜索结果中用户的主播主页地址                    |
| richTitle                 | 字符串 | 搜索结果中专辑的富文本标题                      |
| vipType                   | 整数   | 搜索结果中专辑的VIP类型                         |
| numFound                  | 整数   | 搜索结果的总数量                                |
| start                     | 整数   | 当前结果的起始位置                              |
| totalPage                 | 整数   | 搜索结果的总页数                                |

下面是 `responseHeader` 的参数说明：

| 参数名称 | 数据类型 | 说明                                                         |
| -------- | -------- | ------------------------------------------------------------ |
| QTime    | 整数     | 查询花费时间，单位为毫秒。                                   |
| params   | object   | 包含在请求中的所有参数，包括 core、defType、indent、qf、start、sort、rows、wt。 |
| status   | 整数     | 查询的状态，0表示成功，非0表示出错。                         |

`params`字段表示请求参数信息，它包含了客户端在请求中设置的各种参数的名称和值。以下是params字段中包含的各个参数的具体含义：

| 参数名  | 类型   | 描述                 |
| ------- | ------ | -------------------- |
| core    | 字符串 | 搜索的索引类型。     |
| defType | 字符串 | 查询解析器类型。     |
| indent  | 字符串 | 是否缩进输出。       |
| qf      | 字符串 | 查询字段及其权重。   |
| start   | 字符串 | 结果的起始位置。     |
| sort    | 字符串 | 结果的排序方式。     |
| rows    | 字符串 | 每页返回的结果数量。 |
| wt      | 字符串 | 返回结果的格式。     |

### 返回值说明

#### 请求成功返回示例

```json
{
    "ret": 200,
    "msg": "专辑检索结果",
    "data": {
        "result": {
            "response": {
                "docs": [
                    {
                        "play": 2853604,
                        "user_source": "1",
                        "cover_path": "//imagev2.xmcdn.com/group11/M00/6E/A2/wKgDbVXXIAuQ-laYAAIrwiJmAuw185.jpg!op_type=3&columns=290&rows=290&magick=png",
                        "title": "你好，西藏",
                        "uid": 20401328,
                        "url": "/album/2888955",
                        "pinyin": "qita",
                        "category_id": 1006,
                        "intro": "走进人间天堂~为你讲述阿境四次入藏的点点滴滴~第四季正在更新~~~理论更新时间：每周日晚上~",
                        "id": 2888955,
                        "is_paid": false,
                        "is_finished": 1,
                        "tags": "花样旅行,在路上,旅行者,西藏,本地听",
                        "category_title": "生活",
                        "isDraft": false,
                        "created_at": 1440161954000,
                        "type": "1",
                        "last_uptrack_at_hour": 83095,
                        "is_v": true,
                        "refund_support_type": 0,
                        "count_comment": 155,
                        "score": 9.6,
                        "price_type_id": 0,
                        "updated_at": 1674520933000,
                        "isVipFree": false,
                        "nickname": "阿境",
                        "custom_title": "为你讲述阿境四次入藏的点点滴滴",
                        "verify_type": 1,
                        "vipFreeType": 0,
                        "serialState": 1,
                        "price_type_enum": 0,
                        "tracks": 36,
                        "isNoCopyright": false,
                        "comments_count": 0,
                        "price_types": [],
                        "anchorUrl": "/zhubo/20401328",
                        "richTitle": "<span class =\"orange-1\">你好</span>，西藏",
                        "vipType": 0
                    },
                    {
                    "play": 13669548,
                    "user_source": "1",
                    "cover_path": "//imagev2.xmcdn.com/group82/M07/60/51/wKg5Il9eBZDz_Zs8AAGggBi7K9k542.jpg!op_type=3&columns=290&rows=290&magick=png",
                    "title": "你好，中校先生【军婚｜现言】",
                    "uid": 77359630,
                    "url": "/album/40778098",
                    "pinyin": "youshengshu",
                    "category_id": 3,
                    "intro": "先婚后爱，记者×中校的婚姻攻坚战。【强烈推荐】男女双洁+青春校园+甜宠爽文，欢迎入坑！重生后成了偏执反派的白月光丨校园甜宠丨穿书逆袭丨多人有声剧科幻爱情+平行时空+互相救赎，快来收听！平行人生丨科幻言情多人剧丨杨建东完美爱情小0和她的朋友们：...",
                    "id": 40778098,
                    "is_paid": false,
                    "is_finished": 2,
                    "tags": "",
                    "category_title": "有声书",
                    "isDraft": false,
                    "created_at": 1597156955000,
                    "type": "1",
                    "last_uptrack_at_hour": 84932,
                    "is_v": true,
                    "refund_support_type": 0,
                    "count_comment": 325,
                    "score": 9.5,
                    "price_type_id": 0,
                    "updated_at": 1663840457000,
                    "isVipFree": false,
                    "nickname": "流浪的小0_仓央剧社",
                    "custom_title": "一桩军婚外加一位高深莫测的中校先生",
                    "verify_type": 2,
                    "vipFreeType": 0,
                    "serialState": 2,
                    "price_type_enum": 0,
                    "tracks": 111,
                    "isNoCopyright": false,
                    "comments_count": 0,
                    "price_types": [],
                    "anchorUrl": "/zhubo/77359630",
                    "richTitle": "<span class =\"orange-1\">你好</span>，中校先生【军婚｜现言】",
                    "vipType": 0
                    }],
                "numFound": 23425,
                "totalPage": 1172,
                "start": 0,
                "pageSize": 20,
                "sc": {},
                "total": 23425
            },
            "responseHeader": {
                "QTime": 170,
                "params": {
                    "core": "album",
                    "defType": "edismax",
                    "indent": "on",
                    "qf": "category_title^100 title^80 tags^50 intro^0.001",
                    "start": "0",
                    "sort": "relation",
                    "rows": "20",
                    "wt": "json"
                },
                "status": 0
            }
        }
    }
}
```




