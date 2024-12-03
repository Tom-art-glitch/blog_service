# 标签接口文档

## 1. 创建标签·

### 1.1  接口描述

创建标签。

### 1.2 请求方法

POST /api/v1/tags

### 1.3 输入参数

**Body 参数**

| 参数名称 | 必选 | 类型   | 描述     |
| -------- | ---- | ------ | -------- |
| name     | 是   | String | 标签名称 |
| createdby | 是 | String | 标签创建者 |
| state | 否 | String | 标签状态 |

### 1.4 输出参数

| 参数名称 | 类型 | 描述 |
| ---------| ------ | ---|
| name | String | 标签名字 |
| state | String | 标签状态 |

### 1.5 请求示例

**输入示例**

```bash
curl -X POST http://127.0.0.1:8000/api/v1/tags -F 'name=Go' -F created_by=eddycjy
```

**输出示例**

```json
{
	
}
```

## 2. 删除标签

### 2.1 接口描述

删除指定标签。

### 2.2 请求方法

DELETE /api/v1/tags/:id	

### 2.3 输入参数

**Query 参数**

| 参数名称 | 必选 | 类型   | 描述   |
| :------- | :--- | ------ | ------ |
| id       | 是   | String | 标签id |

### 2.4 输出参数

```json
{

}
```

### 2.5 请求示例

**输入示例**

```bash
curl -X DELETE  http://127.0.0.1:8000/api/v1/tags/{id}
```

**输出示例**

```josn
{}
```



## 3. 修改标签

### 3.1 接口描述

修改指定标签。

### 3.2 请求方法

PUT /api/v1/tags/:id	

### 3.3 输入参数

**Query 参数**

| 参数名称    | 必选 | 类型   | 描述     |
| ----------- | ---- | ------ | -------- |
| name        | 否   | String | 标签名字 |
| modified_by | 是   | String | 修改者   |
| state       | 否   | String | 标签状态 |

**Path 参数**

| 参数名称 | 必选 | 类型   | 描述   |
| -------- | ---- | ------ | ------ |
| id       | 是   | String | 标签ID |

### 3.4 输出参数

```json
{

}
```

### 3.5 请求示例

**输入示例**

```bash
curl -X PUT http://127.0.0.1:8000/api/v1/tags/{id} -F state=0 -F modified_by=eddycjy
```

**输出示例**

```json
{}
```



## 4. 获取标签

### 4.1 接口描述

获取标签列表。

### 4.2 请求方法

GET /api/v1/tags

### 4.3 输入参数

**Body 参数**

| 参数名称 | 必选 | 参数类型 | 描述     |
| -------- | ---- | -------- | -------- |
| name     | 否   | String   | 标签名字 |
| state    | 否   | String   | 标签状态 |

**Query 参数**

| 参数类型  | 必选 | 参数类型 | 描述   |
| --------- | ---- | -------- | ------ |
| page      | 否   | String   | 页数   |
| page_size | 否   | String   | 页大小 |

### 4.4 输出参数

```json
{

}
```

### 4.5 请求示例

**输入示例**

```bash
curl -X GET 'http://127.0.0.1:8000/api/v1/tags?page=1&page_size=2'
```

**输出示例**

```json
{"list":[{"id":1,"created_by":"eddycjy","modified_by":"","created_on":1574493416,"modified_on":1574493416,"deleted_on":0,"is_del":0,"name":"Go 语言","state":1},{"id":2,"created_by":"eddycjy","modified_by":"","created_on":1574493813,"modified_on":1574493813,"deleted_on":0,"is_del":0,"name":"PHP","state":1}],"pager":{"page":1,"page_size":2,"total_rows":3}}
```

