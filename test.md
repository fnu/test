| header 1 | header 2 |
| -------- | -------- |
| cell 1   | cell 2   |
| cell 3   | cell 4   |


# SEO-关键词

## 功能介绍

分析搜索引擎来的关键词.

支持 `开始时间`, `结束时间`, `搜索引擎`, `关键词`, `到达页面` 等过滤条件.

--------

## 列表数据

### 请求方式
GET

### 请求地址
`/seo/keyword/`

### 参数说明
<table>
    <thead>
        <tr>
            <th>abcd</th>
            
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>abcd</td>
        </tr>
    </tbody>
</table>


| 参数名称   | 是否可选 |   类型   |     格式    |  默认值 |  备注     |
|==========|=========|=========|=========== |======= |==========|
| siteid   | **必须** | int     | 123        | [null] | 站点编号   |
| start    | 可选     | string  | YYYY-MM-DD |  今天   | 开始时间   |
| end      | 可选     | string  | YYYY-MM-DD |  今天   | 结束时间   |
| engineid | 可选     | int     | 123        |  0     | 搜索引擎ID (0表示不过滤搜索引擎) |
| keyword  | 可选     | string  | 美女        | [null] | 关键词, 支持 * 号匹配 |
| url      | 可选     | string  | http://... | [null] | 到达页面, 支持 * 号匹配 |
| order    | 可选     | string  | arrival    | arrival | 排序字段, 取值范围[arrival, count_url] |
| page     | 可选     | int     | 123        | 1      | 当前页码, 从1开始 |


### 返回值的 data 说明

| 字段名     | 类型       | 备注       |
|===========|===========|===========|
| siteid    | int       | 站点ID     |
| start     | string    | 开始时间    |
| end       | string    | 结束时间    |
| url       | string    | 到达页面, 参数回传 |
| keyword   | string    | 关键词, 参数回传 |
| engineid  | int       | 搜索引擎ID, 参数回传 |
| page      | int       | 关键词, 参数回传 |
| itemCountPerPage | int  | 页大小 |
| currentPageNumber | int  | 当前页码 |
| pageCount | int | 总页数 |
| list      | array     | 列表          |
| list.keyword| string  | 关键词        |
| list.keyword_em | string| 关键词标红 (只有传了 `keyword` 参数后, 才有 `keyword_em` 字段)  |
| list.arrival | int    | 来访次数      |
| list.url  | string    | 到达页面 (示例, 如果有多个, 也只显示一个)|
| list.count_url | int  | 到达页面数    |



### 返回值示例

```json
{
    "status": true,
    "errno": 0,
    "errmsg": "",
    "data": {
        "siteid": 3,
        "start": "2013-11-09",
        "end": "2013-11-09",
        "url": "",
        "keyword": "情侣壁纸",
        "engineid": 0,
        "order": "arrival",
        "page": 1,
        "itemCountPerPage": 20,
        "currentPageNumber": 1,
        "pageCount": 12,
        "list": [
            {
                "keyword": "情侣壁纸",
                "url": "http://www.8825.com/qinglv/",
                "arrival": "17",
                "count_url": "1",
                "keyword_em": "<em>情侣壁纸</em>"
            },
            ...
         ]
    },
    "timestamp": 1383977088
}
```

--------

## 细分搜索引擎

...

--------

## 来访历史摘要 (趋势图)
...

